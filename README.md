<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>申请信息填写表</title>
  <title>Mẫu đơn điền thông tin ứng dụng</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: "Microsoft YaHei", sans-serif;
    }

    body {
      background-color: #f5f6f8;
      padding: 20px;
    }

    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 24px;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    }

    h2 {
      text-align: center;
      margin-bottom: 24px;
      color: #333;
    }

    .form-group {
      margin-bottom: 16px;
    }

    label {
      display: block;
      margin-bottom: 6px;
      color: #555;
      font-weight: bold;
    }

    input[type="text"],
    select,
    input[type="date"] {
      width: 100%;
      padding: 12px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 16px;
    }

    .file-upload {
      position: relative;
      display: inline-block;
      cursor: pointer;
    }

    .file-button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 48px;
      height: 48px;
      background-color: #FEF3E2;
      color: white;
      font-size: 24px;
      border-radius: 6px;
      transition: background-color 0.3s;
    }

    .file-button:hover {
      background-color: #0056b3;
    }

    .file-input {
      position: absolute;
      left: 0;
      top: 0;
      opacity: 0;
      width: 100%;
      height: 100%;
      cursor: pointer;
    }

    .file-info {
      margin-top: 8px;
      font-size: 14px;
      color: #666;
    }

    .section-title {
      font-weight: bold;
      margin-top: 20px;
      margin-bottom: 10px;
      color: #333;
    }

    .required::after {
      content: " ★";
      color: red;
    }

    .collapse {
      border: 1px solid #ddd;
      border-radius: 6px;
      overflow: hidden;
    }

    .collapse-header {
      background: #f0f0f0;
      padding: 12px;
      cursor: pointer;
      font-weight: bold;
    }

    .collapse-content {
      display: none;
      padding: 12px;
    }

    .custom-input {
      margin-top: 10px;
      display: none;
    }

    .submit-btn {
      width: 100%;
      padding: 14px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 20px;
    }

    .submit-btn:hover {
      background-color: #0056b3;
    }

    @media (max-width: 600px) {
      .container {
        padding: 16px;
      }
    }
  </style>
</head>
<body>

<div class="container">
  <h2>申请信息填写表</h2>

  <!-- 姓名 -->
  <div class="form-group">
    <label class="required">姓名Họ tên</label>
    <input type="text" placeholder="请输入姓名" required />
  </div>

  <!-- 身份证号 -->
  <div class="form-group">
    <label class="required">身份证号Số CMND/CCCD</label>
    <input type="text" placeholder="请输入身份证号码" required />
  </div>

  <!-- 手机号 -->
  <div class="form-group">
    <label class="required">手机号Số điện thoại</label>
    <input type="text" placeholder="请输入手机号码（10~11位）" required />
  </div>

  <!-- 国籍 -->
  <div class="form-group">
    <label class="required">国籍Quốc tịch</label>
    <select id="nationalitySelect" required>
      <option value="">请选择</option>
      <option value="越南">越南Việt Nam</option>
      <option value="中国">中国Trung Quốc</option>
      <option value="其他">自定义Tùy chỉnh</option>
    </select>
    <input type="text" class="custom-input" id="nationalityCustom" placeholder="请输入自定义国籍" />
  </div>

  <!-- 应聘岗位 -->
  <div class="form-group">
    <label class="required">应聘岗位Vị trí ứng tuyển</label>
    <select id="positionSelect" required>
      <option value="">请选择</option>
      <option value="普通工人">普通工人Công nhân thường</option>
      <option value="自动化">自动化Tự động hóa</option>
      <option value="点胶">点胶Phun keo</option>
      <option value="电工">电工Thợ điện</option>
      <option value="钳工">钳工Thợ nguội</option>
      <option value="其他">自定义Tùy chỉnh</option>
    </select>
    <input type="text" class="custom-input" id="positionCustom" placeholder="请输入自定义岗位" />
  </div>

  <!-- 工作年限 -->
  <div class="form-group">
    <label class="required">工作年限Kinh nghiệm làm việc</label>
    <select id="experienceSelect" required>
      <option value="">请选择</option>
      <option value="1年以下">1年以下Dưới 1 năm</option>
      <option value="1-3年">1-3年1-3 năm</option>
      <option value="3-5年">3-5年3-5 năm</option>
      <option value="5年以上">5年以上Trên 5 năm</option>
      <option value="其他">自定义Tùy chỉnh</option>
    </select>
    <input type="text" class="custom-input" id="experienceCustom" placeholder="请输入自定义年限" />
  </div>

  <!-- 证件上传标题 -->
  <div class="section-title">证件上传Tài liệu đính kèm</div>

  <!-- 护照照片 -->
  <div class="form-group">
    <label>护照照片Ảnh hộ chiếu</label>
    <div class="file-upload">
      <div class="file-button">➕</div>
      <input type="file" class="file-input" onchange="showFileName(this, 'passportFileText')" />
    </div>
    <div class="file-info" id="passportFileText">请添加文件 / Vui lòng thêm tập tin</div>
  </div>

  <!-- 证件照 -->
  <div class="form-group">
    <label class="required">证件照（头像）Ảnh thẻ</label>
    <div class="file-upload">
      <div class="file-button">➕</div>
      <input type="file" class="file-input" onchange="showFileName(this, 'avatarFileText')" required />
    </div>
    <div class="file-info" id="avatarFileText">请添加文件 / Vui lòng thêm tập tin</div>
  </div>

  <!-- 身份证正面 -->
  <div class="form-group">
    <label class="required">身份证正面Mặt trước CMND</label>
    <div class="file-upload">
      <div class="file-button">➕</div>
      <input type="file" class="file-input" onchange="showFileName(this, 'idFrontFileText')" required />
    </div>
    <div class="file-info" id="idFrontFileText">请添加文件 / Vui lòng thêm tập tin</div>
  </div>

  <!-- 身份证反面 -->
  <div class="form-group">
    <label class="required">身份证反面Mặt sau CMND</label>
    <div class="file-upload">
      <div class="file-button">➕</div>
      <input type="file" class="file-input" onchange="showFileName(this, 'idBackFileText')" required />
    </div>
    <div class="file-info" id="idBackFileText">请添加文件 / Vui lòng thêm tập tin</div>
  </div>

  <!-- 签证信息折叠面板 -->
  <div class="collapse">
    <div class="collapse-header" onclick="toggleCollapse()">▶ 签证信息（可选）Thông tin visa (tùy chọn)</div>
    <div class="collapse-content" id="visaInfo">
      <div class="form-group">
        <label>签证类型Loại visa</label>
        <select>
          <option value="">请选择</option>
          <option value="旅游签证">旅游签证Du lịch</option>
          <option value="商务签证">商务签证Công tác</option>
          <option value="学生签证">学生签证Học sinh</option>
          <option value="其他">自定义Tùy chỉnh</option>
        </select>
      </div>

      <div class="form-group">
        <label>签证开始日期Ngày bắt đầu</label>
        <input type="date" />
      </div>

      <div class="form-group">
        <label>签证结束日期Ngày kết thúc</label>
        <input type="date" />
      </div>
    </div>
  </div>

  <!-- 提交按钮 -->
  <button class="submit-btn">提交申请Gửi đơn đăng ký</button>
</div>

<script>
  function toggleCollapse() {
    const content = document.getElementById('visaInfo');
    content.style.display = content.style.display === 'none' ? 'block' : 'none';
  }

  // 显示文件名逻辑
  function showFileName(input, infoId) {
    const fileText = document.getElementById(infoId);
    if (input.files && input.files[0]) {
      fileText.textContent = input.files[0].name;
    } else {
      fileText.textContent = '请添加文件 / Vui lòng thêm tập tin';
    }
  }

  // 自定义输入框逻辑
  function setupCustomInput(selectId, inputId) {
    const select = document.getElementById(selectId);
    const input = document.getElementById(inputId);

    select.addEventListener('change', () => {
      if (select.value === '其他') {
        input.style.display = 'block';
      } else {
        input.style.display = 'none';
      }
    });
  }

  setupCustomInput('nationalitySelect', 'nationalityCustom');
  setupCustomInput('positionSelect', 'positionCustom');
  setupCustomInput('experienceSelect', 'experienceCustom');
</script>

</body>
</html>
