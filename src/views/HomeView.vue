<script setup lang="ts"></script>

<template>
  <!-- 히어로 섹션 -->
  <section class="relative rounded-xl overflow-hidden mb-12">
    <div class="flex flex-col md:flex-row items-center">
      <div class="md:w-1/2 p-8 md:p-12 bg-gradient-to-r from-blue-50 to-blue-100 z-10">
        <h1 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
          함께하는 일정 계획,<br />더 쉽고 즐겁게
        </h1>
        <p class="text-gray-600 mb-8 text-lg">
          친구, 가족, 동료와의 모임을 위한 일정 조율부터<br />
          장소 선택, 예약까지 한번에 해결하세요.
        </p>
        <button
          class="bg-blue-600 hover:bg-blue-700 text-white py-3 px-8 rounded-lg font-medium text-lg shadow-lg transform transition hover:-translate-y-1 !rounded-button whitespace-nowrap cursor-pointer"
        >
          새 모임 만들기 <i class="fas fa-arrow-right ml-2"></i>
        </button>
      </div>
      <div class="md:w-1/2 h-full">
        <img
          src="https://readdy.ai/api/search-image?query=A%20modern%2C%20clean%20image%20showing%20a%20group%20of%20diverse%20friends%20planning%20a%20trip%20together%2C%20using%20digital%20devices%2C%20with%20a%20calendar%20interface%20visible.%20The%20scene%20has%20a%20light%20blue%20gradient%20background%20with%20subtle%20abstract%20shapes%2C%20conveying%20organization%20and%20collaboration.%20High%20quality%2C%20photorealistic%20style.&width=800&height=600&seq=1&orientation=landscape"
          alt="함께 계획하는 모습"
          class="w-full h-full object-cover object-top"
        />
      </div>
    </div>
  </section>

  <!-- 서비스 특징 섹션 -->
  <section class="mb-12">
    <h2 class="text-2xl font-bold text-gray-800 mb-8 text-center">
      Grouping으로 더 쉽게 모임을 계획하세요
    </h2>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <div class="bg-white rounded-xl shadow-md p-6 text-center">
        <div
          class="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4"
        >
          <i class="fas fa-calendar-check text-blue-600 text-2xl"></i>
        </div>
        <h3 class="text-xl font-bold text-gray-800 mb-3">간편한 일정 조율</h3>
        <p class="text-gray-600">
          모든 참여자의 가능한 일정을 한눈에 확인하고, 최적의 날짜를 자동으로 추천해 드립니다.
        </p>
      </div>

      <div class="bg-white rounded-xl shadow-md p-6 text-center">
        <div
          class="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4"
        >
          <i class="fas fa-map-marker-alt text-blue-600 text-2xl"></i>
        </div>
        <h3 class="text-xl font-bold text-gray-800 mb-3">맞춤형 장소 추천</h3>
        <p class="text-gray-600">
          선택한 날짜와 지역에 맞는 맛집, 관광지, 숙소를 데이터 기반으로 추천해 드립니다.
        </p>
      </div>

      <div class="bg-white rounded-xl shadow-md p-6 text-center">
        <div
          class="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4"
        >
          <i class="fas fa-clipboard-list text-blue-600 text-2xl"></i>
        </div>
        <h3 class="text-xl font-bold text-gray-800 mb-3">완벽한 일정표 제공</h3>
        <p class="text-gray-600">
          모임의 모든 계획을 한눈에 볼 수 있는 일정표를 자동으로 생성하고 공유할 수 있습니다.
        </p>
      </div>
    </div>
  </section>

  <!-- CTA 섹션 -->
  <section class="bg-blue-600 rounded-xl p-8 md:p-12 text-center mb-12">
    <h2 class="text-2xl md:text-3xl font-bold text-white mb-4">지금 바로 시작하세요!</h2>
    <p class="text-blue-100 mb-8 max-w-2xl mx-auto">
      더 이상 복잡한 일정 조율과 계획에 시간을 낭비하지 마세요. Grouping과 함께 더 쉽고 즐거운
      모임을 경험하세요.
    </p>
    <button
      class="bg-white text-blue-600 hover:bg-blue-50 py-3 px-8 rounded-lg font-medium text-lg shadow-lg transform transition hover:-translate-y-1 !rounded-button whitespace-nowrap cursor-pointer"
    >
      무료로 시작하기
    </button>
  </section>
</template>
