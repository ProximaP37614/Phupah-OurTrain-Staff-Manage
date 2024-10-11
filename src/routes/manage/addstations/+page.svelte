<script>
  let stId = '';
  let stName = '';
  let stAddress = '';
  let stTime = '';
  </script>
  
  <div class="flex px-8 lg:px-12 justify-center bg-white">
    <div class="container mx-auto p-4">
        <h1 class="text-3xl font-bold mb-8 text-center text-[#102C57] underline">จัดการเที่ยวโดยสาร</h1>
        <h2 class="text-xl font-bold mb-4">เที่ยวโดยสารปัจจุบัน</h2>
        <div class="grid grid-cols-4 gap-4">
          <input
            type="text"
            bind:value={stId}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="รหัสสถานี"
          />
          <input
            type="text"
            bind:value={stName}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="ชื่อสถานี"
          />
          <input
            type="text"
            bind:value={stAddress}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="ที่อยู่สถานี"
          />
          <input
            type="text"
            bind:value={stTime}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="ระยะเวลา"
          />   
        </div>
        <div class="flex justify-center items-center">
        <button class=" text-xl mt-8 bg-[#102C57] px-8 py-2.5 text-white rounded-lg hover:bg-blue-800">ยืนยัน</button>
      </div>
      </div>
  </div>