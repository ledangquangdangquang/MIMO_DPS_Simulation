# Mô phỏng ước lượng kênh MIMO

1. Cấu trúc dự án 
```
MIMO_DPS_Simulation/
├── main_siso_flat.m          % Kịch bản A: SISO phẳng tần số
├── main_siso_sel.m            % Kịch bản B: SISO chọn lọc tần số
├── main_mimo_8x8.m            % Kịch bản C: MIMO 8x8 (hybrid + full)
├── functions/
│   ├── gen_mpc_parameters.m   % Sinh tham số MPC (Doppler, delay, AoA, AoD, complex weight)
│   ├── soce_channel.m         % Tính kênh theo SoCE trực tiếp
│   ├── dps_1d_basis.m         % Tính ma trận DPS 1D và trị riêng (gọi dpss của MATLAB)
│   ├── gamma_approx_1d.m      % Tính vector gamma xấp xỉ (tilde_gamma) cho một MPC
│   ├── dps_1d_approx_coeff.m  % Tính toàn bộ hệ số alpha xấp xỉ cho một khối (tổng hợp các gamma)
│   ├── dps_reconstruct.m      % Từ hệ số alpha và ma trận V, tái tạo kênh
│   └── utils/
│       ├── calc_doppler.m     % Doppler từ vận tốc, góc, fc
│       ├── calc_delay.m       % Delay từ khoảng cách
│       └── plot_results.m     % Vẽ biểu đồ sai số, độ phức tạp
└── data/                      % Lưu các ma trận DPS đã tính (cache)
```
