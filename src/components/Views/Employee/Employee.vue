<template>
 <div>
      <div class="page-title">
        <div class="page-left">Danh sách nhân viên</div>
        <div class="page-right">
          <button id="btnAdd" class="btn-default" >Thêm nhân viên</button>
        </div>
      </div>
      <div class="toolbar">
        <input
        type="text" 
        class="input-search" 
        tyle="width: 220px" 
        placeholder="Tìm kiếm theo mã, tên khách hàng"
        />
        <button class="btn-refresh"></button>
      </div>
      <div class="grid">
        <table id="tblListCustomer" class="table" width="100%" border="0">
          <thead>
            <tr>
              <th>Mã nhân viên</th>
              <th>Họ và tên</th>
              <th>Giới tính</th>
              <th>Ngày sinh</th>
              <th>Chức vụ</th>
              <th>Điện thoại</th>
              <th>Email</th>
              <th class="text-align-right">Số tiền lương</th>
              <th class="text-align-center">Đang hoạt động</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>NV001</td>
              <td>Nguyễn Văn Mạnh</td>
              <td>Nam</td>
              <td>22/09/1999</td>
              <td>Nhân viên</td>
              <td>0961179969</td>
              <td>manhnv229@gmail.com</td>
              <td class="text-align-right">10.025.000</td>
              <td class="text-align-center">
                Đang làm việc
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="paging">
        <div data-v-a72348a4="" class="paging-bar">
          <div data-v-a72348a4="" class="paging-record-info">
            Hiển thị <b data-v-a72348a4="">1-10/1000</b> nhân viên
          </div>
          <div data-v-a72348a4="" class="paging-option">
            <div
              data-v-a72348a4=""
              class="btn-select-page m-btn-firstpage"
            ></div>
            <div
              data-v-a72348a4=""
              class="btn-select-page m-btn-prev-page"
            ></div>
            <div data-v-a72348a4="" class="m-btn-list-page">
              <button ref="btn-page" data-v-a72348a4="" class="btn-pagenumber">1</button>
              <button ref="btn-page" data-v-a72348a4="" class="btn-pagenumber">2</button>
              <button ref="btn-page" data-v-a72348a4="" class="btn-pagenumber">3</button>
              <button ref="btn-page" data-v-a72348a4="" class="btn-pagenumber">4</button>
            </div>
            <div 
              data-v-a72348a4=""
              class="btn-select-page m-btn-next-page"
            ></div>
            <div
              data-v-a72348a4=""
              class="btn-select-page m-btn-lastpage"
            ></div>
          </div>
          <div data-v-a72348a4="" class="paging-record-option">
            <b data-v-a72348a4="">10</b> nhân viên/trang
          </div>
        </div>
      </div>
    </div>
</template>
