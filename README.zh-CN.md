[English project overview](README.md)

# DIKWP ALOGOS FIELD OS 交付说明

Created by Yucong Duan (段玉聪).

## 系统定位

DIKWP ALOGOS FIELD OS 是一个机器原生无言场交换系统。核心运行时不把句子或 Token 作为模型间交换载荷，而使用：

- 高维振幅；
- 复相位；
- 显著性；
- 耦合拓扑；
- 吸引子状态；
- Residual；
- 跨表示空间数值桥。

系统定义：

- AFP/1.0 数值场包；
- AFB/1.0 固定宽度场字节码；
- FieldState 五部分机器场；
- AttractorBank 吸引子动力学；
- LatentBridge 跨空间映射；
- Mesh 4.0 Three-No 数值闭包。

## 主要文件

- `DIKWP-ALOGOS-FIELD-OS_Source_0.1.0-alpha.zip`：完整源码；
- `DIKWP-ALOGOS-AFP-AFB-1.0_Protocol_Bundle.zip`：协议、Schema和示例；
- `DIKWP_ALOGOS_FIELD_OS_技术白皮书_CN.pdf`：18页技术白皮书；
- `DIKWP_ALOGOS_FIELD_OS_技术白皮书_CN.docx`：可编辑白皮书；
- `DIKWP_ALOGOS_Architecture.png/.svg`：系统架构图；
- `VERIFICATION_REPORT.json`：最终综合验证；
- `CLEAN_ROOM_REPORT.json`：干净环境运行结果；
- `SCHEMA_CONFORMANCE_REPORT.json`：协议Schema验证；
- `API_SMOKE_REPORT.json`：只读API冒烟测试；
- `A11Y_REPORT.json`：DOCX可访问性审计；
- `MANIFEST.sha256`：交付文件摘要。

## 五分钟运行

```bash
unzip DIKWP-ALOGOS-FIELD-OS_Source_0.1.0-alpha.zip
cd DIKWP-ALOGOS-FIELD-OS

python -m venv .venv
. .venv/bin/activate
python -m pip install -e .

python -m dikwp_alogos demo
python -m dikwp_alogos verify
python -m unittest discover -s tests -v
```

## 固定演示指标

- 绑定/解绑定往返余弦：1.000000；
- 源吸引子代码：502；
- 目标吸引子代码：502；
- 目标吸引子相似度：约0.99999999；
- 跨空间保留集平均余弦：约0.993826；
- 反向恢复相似度：约0.444393；
- Mesh 4.0闭包：S3；
- 自动化测试：35/35通过。

保留集指标来自确定性合成线性夹具，只验证软件实现路径。128维压缩到96维造成的反向损失被保留在S3闭包中。

## 项目归属

本交付是为段玉聪审阅准备的独立候选实现。正式进入其GitHub前，仍需确认项目名称、作者归属、许可证、维护者和安全联系人。
