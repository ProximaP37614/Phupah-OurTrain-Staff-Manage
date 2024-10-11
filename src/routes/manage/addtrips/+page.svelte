<script>
  let tripCode = '';
  let trainCode = '';
  let passengerCount = '';
  let ticketClass = '';
  let route = '';
  let startStation = '';
  let endStation = '';
  let travelTime = '';
  let trainNo = '';
  let seatingClass = '';
  let seatType1 = '';
  let seatCount1 = '';
  let seatType2 = '';
  let seatCount2 = '';
  let employees = [{ emId: '', emName: '' }];

  function addEmployee() {
    employees = [...employees, { emId: '', emName: '' }];
  }

  function removeEmployee(index) {
    employees = employees.filter((_, i) => i !== index);
  }
  </script>
  
  <div class="flex px-8 lg:px-12 justify-center bg-white">
    <div class="container mx-auto p-4">
        <h1 class="text-3xl font-bold mb-8 text-center text-[#102C57] underline">จัดการเที่ยวโดยสาร</h1>
        <h2 class="text-xl font-bold mb-4">เที่ยวโดยสารปัจจุบัน</h2>
        <div class="grid grid-cols-4 gap-4">
          <input
            type="text"
            bind:value={tripCode}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="รหัสเที่ยวโดยสาร"
          />
          <input
            type="text"
            bind:value={trainCode}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="รหัสรถไฟ"
          />
          <input
            type="text"
            bind:value={passengerCount}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="จำนวนขบวน"
          />
          <select
            bind:value={ticketClass}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
          >
            <option value="">ประเภทชั้นโดยสาร</option>
            <option value="first">First Class</option>
            <option value="second">Second Class</option>
          </select>
        
          <select
            bind:value={route}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
          >
            <option value="">เส้นทางโดยสาร</option>
            <option value="route1">Route 1</option>
            <option value="route2">Route 2</option>
          </select>
        
          <select
            bind:value={startStation}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
          >
            <option value="">สถานีต้นทาง</option>
            <option value="station1">Station 1</option>
            <option value="station2">Station 2</option>
          </select>
        
          <select
            bind:value={endStation}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
          >
            <option value="">สถานีปลายทาง</option>
            <option value="station1">Station 1</option>
            <option value="station2">Station 2</option>
          </select>
        </div>
        <div class="flex mt-6">
          <label class="block">
          <span>วัน/เวลา ออกเดินทาง</span>
          <input
            type="datetime-local"
            bind:value={travelTime}
            class="border border-gray-300 rounded-md px-4 py-6 text-gray-500"
            placeholder="วันที่เดินทาง"
          />
        </label>
        </div>
        <div class="grid grid-cols-6 gap-4 mt-6">
          <label class="block">
            <input
              type="text"
              bind:value={trainNo}
              class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-full"
              placeholder="รหัสขบวน"
            />
          </label>
          <label class="block">
            <select
              bind:value={seatingClass}
              class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-full"
            >
              <option value="">ชั้นโดยสาร</option>
              <option value="economy">Economy</option>
              <option value="business">Business</option>
            </select>
          </label>
          <label class="block">
            <select
              bind:value={seatType1}
              class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-full"
            >
              <option value="">ประเภทที่นั่ง</option>
              <option value="window">Window</option>
              <option value="aisle">Aisle</option>
            </select>
          </label>
          <label class="block">
            <input
              type="number"
              bind:value={seatCount1}
              class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-full"
              placeholder="จำนวนที่นั่ง"
            />
          </label>
          <label class="block">
            <select
              bind:value={seatType2}
              class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-full"
            >
              <option value="">ประเภทที่นั่ง</option>
              <option value="window">Window</option>
              <option value="aisle">Aisle</option>
            </select>
          </label>
          <label class="block">
            <input
              type="number"
              bind:value={seatCount2}
              class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-full"
              placeholder="จำนวนที่นั่ง"
            />
          </label>
        </div>
        <div class="flex px-8 lg:px-12 justify-center bg-white">
          <div class="container mx-auto p-4">
            <!-- Employee Input Fields -->
            {#each employees as employee, index}
              <div class="flex mt-6 space-x-4">
                <input
                  type="text"
                  bind:value={employee.emId}
                  class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-1/4"
                  placeholder="รหัสพนักงานตรวจตั๋วโดยสาร"
                />
                <input
                  type="text"
                  bind:value={employee.emName}
                  class="border border-gray-300 rounded-md px-4 py-6 text-gray-500 w-3/4"
                  placeholder="ชื่อ-สกุลพนักงาน"
                />
                <button
                  class="text-red-600 hover:text-red-800"
                  on:click={() => removeEmployee(index)}
                >
                  ลบ
                </button>
              </div>
            {/each}
        
            <div class="flex flex-col items-center mt-6">
              <!-- Plus icon -->
              <button on:click={addEmployee} class="text-5xl text-blue-900">+</button>
        
              <!-- Text "เพิ่มพนักงาน" -->
              <div class="text-xl text-blue-900 mt-2">เพิ่มพนักงาน</div>
        
              <!-- Underline -->
              <div class="w-28 h-1 bg-blue-900 mt-1"></div>
        
              <button class="text-xl mt-8 bg-[#102C57] px-8 py-2.5 text-white rounded-lg hover:bg-blue-800">
                ยืนยัน
              </button>
            </div>
          </div>
        </div>
    </div>
  </div>