<!-- The exported code uses Tailwind CSS. Install Tailwind CSS in your dev environment to ensure all styles work. -->
<template>
  <div class="min-h-screen bg-gray-50">
    <div class="flex flex-col min-h-screen">
      <!-- 상단 이미지 섹션 -->
      <div class="w-full h-[400px] relative overflow-hidden bg-[#E6F4F1]">
        <img
          src="https://readdy.ai/api/search-image?query=A%20warm%20and%20inviting%20scene%20of%20diverse%20people%20collaborating%20in%20a%20modern%20office%20space%2C%20showing%20teamwork%20and%20community.%20People%20gathered%20around%20a%20table%20discussing%20ideas%2C%20with%20natural%20lighting%20and%20contemporary%20interior%20design.%20The%20image%20has%20soft%2C%20natural%20colors%20and%20creates%20a%20welcoming%20atmosphere&width=1440&height=800&seq=3&orientation=landscape"
          alt="People collaborating"
          class="w-full h-full object-cover"
        />
      </div>
      <!-- 하단 로그인 폼 섹션 -->
      <div class="w-full flex flex-col flex-grow bg-white">
        <div class="flex justify-between items-center p-6 max-w-lg mx-auto w-full"></div>
        <div class="flex-grow flex flex-col justify-start px-4 sm:px-8 pb-8 -mt-8">
          <div class="max-w-lg mx-auto w-full bg-white rounded-2xl p-8 shadow-sm">
            <h1 class="text-3xl font-bold text-gray-900 mb-2">Welcome to Grouping</h1>
            <p class="text-gray-600 mb-12">Continue with your social account</p>
            <div class="space-y-4">
              <button
                @click="handleSocialLogin('google')"
                class="w-full bg-white border border-gray-300 text-gray-700 py-4 px-4 rounded-lg flex items-center justify-center space-x-3 hover:bg-gray-50 transition !rounded-button whitespace-nowrap cursor-pointer"
              >
                <i class="fab fa-google text-xl"></i>
                <span>Continue with Google</span>
              </button>
              <button
                @click="handleSocialLogin('kakao')"
                class="w-full bg-[#FEE500] text-[#000000] py-4 px-4 rounded-lg flex items-center justify-center space-x-3 hover:opacity-90 transition !rounded-button whitespace-nowrap cursor-pointer"
              >
                <i class="fas fa-comment text-xl"></i>
                <span>Continue with Kakao</span>
              </button>
              <button
                @click="handleSocialLogin('naver')"
                class="w-full bg-[#03C75A] text-white py-4 px-4 rounded-lg flex items-center justify-center space-x-3 hover:opacity-90 transition !rounded-button whitespace-nowrap cursor-pointer"
              >
                <span class="text-xl font-bold">N</span>
                <span>Continue with Naver</span>
              </button>
            </div>
          </div>
        </div>
        <div class="max-w-lg mx-auto w-full px-4 py-6 text-center text-sm text-gray-600">
          By continuing, you agree to our
          <a href="#" class="text-blue-600 hover:underline">Terms of Service</a>
          and
          <a href="#" class="text-blue-600 hover:underline">Privacy Policy</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
let tokenClient: any = null

const handleSocialLogin = (provider: string) => {
  if (provider === 'google') {
    if (!tokenClient) {
      tokenClient = window.google.accounts.oauth2.initTokenClient({
        client_id: '759530149928-99h301igs9pmcragspj1bcr755r2pt0h.apps.googleusercontent.com',
        scope: 'openid email profile',
        callback: handleGoogleCredential,
      })
    }

    tokenClient.requestAccessToken()
  }
}

const handleGoogleCredential = async (response: any) => {
  console.log('Google access_token response:', response)

  const accessToken = response.access_token
  if (!accessToken) {
    alert('Google 로그인에 실패했습니다.')
    return
  }

  try {
    const res = await fetch('http://localhost:8080/oauth/google', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ accessToken }), // 백엔드에서 accessToken 처리
    })

    if (!res.ok) throw new Error('Login failed')
    const data = await res.json()

    localStorage.setItem('accessToken', data.token)
    alert('로그인 성공!')

    // TODO: router.push('/dashboard') 등 페이지 이동
  } catch (err) {
    console.error('Login error', err)
    alert('Google 로그인에 실패했습니다.')
  }
}
</script>

<style scoped>
/* Custom scrollbar styling */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}
::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 10px;
}
::-webkit-scrollbar-thumb {
  background: #c5c5c5;
  border-radius: 10px;
}
::-webkit-scrollbar-thumb:hover {
  background: #a0a0a0;
}
/* Remove number input arrows */
input[type='number']::-webkit-inner-spin-button,
input[type='number']::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
