# KERAIA - Knowledge Engineering and Reference AI Architecture

## Tổng quan / Overview

KERAIA là một framework phát triển cho kỹ thuật tri thức tượng trưng (symbolic knowledge engineering) được thiết kế để giải quyết các thách thức về biểu diễn, lập luận và thực thi tri thức trong môi trường phức tạp và động.

KERAIA is a framework for symbolic knowledge engineering designed to address the challenges of representing, reasoning with, and executing knowledge in dynamic and complex environments.

## Bắt đầu nhanh / Quick Start

```bash
# 1. Clone repository
git clone https://github.com/tungleqb/keraia.git
cd keraia

# 2. Chạy Python demo (Khuyến nghị) / Run Python demo (Recommended)
pip install -r requirements.txt
cd impl/causal
python main.py

# 3. Các demo Java cần được điều chỉnh để chạy đầy đủ
# Java demos require adjustments to run fully
# Xem phần "How to Run" bên dưới để biết chi tiết
# See "How to Run" section below for details
```

**Lưu ý / Note**: Python implementation là cách dễ nhất để bắt đầu. Các file Java trong repository chứa code mẫu và cần được tổ chức thành project hoàn chỉnh để chạy.

**Note**: The Python implementation is the easiest way to get started. The Java files in the repository contain sample code and need to be organized into a complete project to run.

### Các tính năng chính / Key Features

- **Clouds of Knowledge**: Tích hợp các nguồn tri thức đa dạng / Integrate diverse knowledge sources
- **Knowledge Lines (KLines) & Lines of Thought (LoTs)**: Tăng cường tính minh bạch và khả năng truy xuất trong ra quyết định / Enhanced transparency and traceability in decision-making
- **Dynamic Relations (Drels)**: Mở rộng ontology truyền thống với chia sẻ thuộc tính nhạy cảm ngữ cảnh / Extended ontologies with context-sensitive property sharing
- **Multi-Paradigm Reasoning**: Hỗ trợ nhiều kỹ thuật suy luận / Support for multiple inference techniques
- **Explainable AI**: Nhấn mạnh tính minh bạch và khả năng giải thích / Emphasis on transparency and explainability

### Các trường hợp sử dụng / Use Cases

1. **Naval Warfare Scenarios**: Kịch bản tác chiến hải quân
2. **Water Treatment Plant Diagnostics**: Chẩn đoán nhà máy xử lý nước
3. **Strategic Decision-Making**: Ra quyết định chiến lược

## Yêu cầu hệ thống / Prerequisites

### Cho các ví dụ Java / For Java Examples

- **Java Development Kit (JDK)**: Phiên bản 11 trở lên / Version 11 or higher
- **Apache Jena**: Phiên bản 4.7.0 trở lên / Version 4.7.0 or higher - Thư viện cho xử lý ontology / Library for ontology processing
- **Neo4j Java Driver**: Phiên bản 5.0.0 trở lên / Version 5.0.0 or higher - Cho tương tác với knowledge graph / For knowledge graph interaction
- **Maven hoặc Gradle** (khuyến nghị): Để quản lý dependencies / For dependency management

### Cho các ví dụ Python / For Python Examples

- **Python**: Phiên bản 3.8 trở lên / Version 3.8 or higher
- **Các thư viện Python cần thiết / Required Python libraries**:
  ```bash
  pip install numpy networkx dowhy pandas
  ```

### Cho Knowledge Graph / For Knowledge Graph

- **Neo4j Database**: Phiên bản 4.x hoặc 5.x / Version 4.x or 5.x
- **APOC Plugin**: Cho các chức năng mở rộng / For extended functionality

### Cho Rule-Based Reasoning / For Rule-Based Reasoning

- **CLIPS**: CLIPS Expert System Shell

## Cài đặt / Installation

### Bước 1: Clone repository / Clone the Repository

```bash
git clone https://github.com/tungleqb/keraia.git
cd keraia
```

### Bước 2: Cài đặt Python Dependencies / Install Python Dependencies

```bash
# Cách 1: Cài đặt từ requirements.txt / Method 1: Install from requirements.txt
pip install -r requirements.txt

# Cách 2: Cài đặt thủ công / Method 2: Manual installation
pip install numpy networkx dowhy pandas
```

### Bước 3: Cài đặt Neo4j (Tùy chọn) / Install Neo4j (Optional)

1. Tải và cài đặt Neo4j từ / Download and install Neo4j from: https://neo4j.com/download/
2. Khởi động Neo4j và tạo database mới / Start Neo4j and create a new database
3. Cài đặt APOC plugin nếu cần / Install APOC plugin if needed
4. Cấu hình thông tin đăng nhập trong code (mặc định: username=`neo4j`, password=`password`) / Configure credentials in code (default: username=`neo4j`, password=`password`)

### Bước 4: Cài đặt CLIPS (Tùy chọn) / Install CLIPS (Optional)

- **Linux/macOS**:
  ```bash
  # Ubuntu/Debian
  sudo apt-get install clips
  
  # macOS với Homebrew
  brew install clips
  ```

- **Windows**: Tải từ / Download from: https://sourceforge.net/projects/clipsrules/

## Cách chạy / How to Run

### 1. Chạy Java Naval Scenario Demo / Running Java Naval Scenario Demo

**Lưu ý quan trọng / Important Note**: Các file Java trong repository hiện tại chứa code mẫu và demo concepts. File `main.java` chứa một demo hoàn chỉnh có thể chạy được, nhưng các file khác có thể cần điều chỉnh.

**Important Note**: The Java files in the current repository contain sample code and demo concepts. The `main.java` file contains a complete runnable demo, but other files may need adjustments.

#### Phương pháp 1: Biên dịch và chạy trực tiếp / Method 1: Direct Compilation and Execution

```bash
cd impl

# Biên dịch (cần có tất cả dependencies trong classpath)
# Compile (requires all dependencies in classpath)
javac -cp ".:path/to/jena.jar:path/to/neo4j-driver.jar" main.java

# Chạy
# Run
java -cp ".:path/to/jena.jar:path/to/neo4j-driver.jar" NavalCloudElaborationDemo
```

**Lưu ý / Note**: Bạn cần tải và thêm các JAR files sau vào classpath:
- Apache Jena (từ / from: https://jena.apache.org/download/)
- Neo4j Java Driver (từ / from: https://neo4j.com/developer/java/)
- Các custom packages như `aip.maps.KS` và `ksconvocation.KSFrame` cũng cần được implement

**Note**: You need to download and add the following JAR files to classpath, plus implement custom packages:
- Apache Jena (version 4.7.0+), Neo4j Java Driver (version 5.0.0+)
- Custom packages like `aip.maps.KS` and `ksconvocation.KSFrame` are defined in the `impl/keraia/` subdirectories
- These custom packages are part of the KERAIA framework and need to be compiled first

#### Phương pháp 2: Sử dụng Maven / Method 2: Using Maven (Experimental)

**File `impl/pom.xml` được cung cấp như một template / A `impl/pom.xml` file is provided as a template**

**Lưu ý / Note**: Hiện tại, các file Java cần được tổ chức lại để biên dịch thành công với Maven. File pom.xml được cung cấp như một điểm khởi đầu.

**Note**: Currently, the Java files need to be reorganized to compile successfully with Maven. The pom.xml file is provided as a starting point.

```bash
cd impl

# Thử biên dịch / Try to compile
mvn clean compile

# Lưu ý: Có thể gặp lỗi do cấu trúc code hiện tại
# Note: May encounter errors due to current code structure
```

**Khuyến nghị / Recommendation**: Sử dụng Python implementation để thử nghiệm framework nhanh chóng. Java implementation phù hợp hơn cho việc nghiên cứu và phát triển.

**Recommendation**: Use the Python implementation for quick experimentation with the framework. The Java implementation is better suited for research and development.

#### Kết quả mong đợi / Expected Output

**Lưu ý / Note**: Kết quả dưới đây là từ concept code. Để chạy thực tế, cần implement đầy đủ các dependencies.

**Note**: The output below is from concept code. To run in practice, full dependencies need to be implemented.

Chương trình sẽ hiển thị / The program would display:
- Cloud A: Các nguồn tri thức ban đầu / Initial knowledge sources
- Cloud B: Các tri thức đã được tinh chỉnh sau khi elaboration / Refined knowledge after elaboration
- Thông tin về sonar detection, radar detection, threat probability, fleet positioning, v.v. / Information about sonar detection, radar detection, threat probability, fleet positioning, etc.

**Khuyến nghị / Recommendation**: Để xem demo hoạt động thực tế, hãy sử dụng Python implementation (bên dưới).

**Recommendation**: To see a working demo, use the Python implementation (below).

### 2. Chạy Python Causal Reasoning Demo / Running Python Causal Reasoning Demo ✅

**Đây là cách dễ nhất và được khuyến nghị để thử nghiệm KERAIA / This is the easiest and recommended way to try KERAIA**

```bash
cd impl/causal

# Chạy demo causal reasoning
# Run causal reasoning demo
python main.py
```

**Kết quả mong đợi / Expected Output**:
```
Estimand type: EstimandType.NONPARAMETRIC_ATE

### Estimand : 1
Estimand name: backdoor
Estimand expression:
    d                                           
─────────(E[KS-FC3|KS-TR2,KS-TR5,KS-TR4,KS-TR3])
d[KS-TR1]

Causal Effect Estimate: *** Causal Estimate ***
Mean value: -0.038
...
```

Chương trình sẽ:
- Mô phỏng kịch bản hải quân với causal relationships / Simulate naval scenarios with causal relationships
- Tính toán probabilistic dependencies giữa các knowledge sources / Calculate probabilistic dependencies between knowledge sources
- Thực hiện Bayesian fusion và causal inference / Perform Bayesian fusion and causal inference
- Hiển thị kết quả ước lượng nhân quả / Display causal estimation results

### 3. Chạy Knowledge Graph với Neo4j / Running Knowledge Graph with Neo4j

#### Bước 1: Khởi động Neo4j / Start Neo4j

```bash
neo4j start
```

#### Bước 2: Chạy Cypher queries / Run Cypher Queries

Mở Neo4j Browser (thường là http://localhost:7474) và chạy các queries từ:

```bash
# Xem full knowledge graph script
# View full knowledge graph script
cat impl/kgraph/full.cypher
```

Hoặc load trực tiếp / Or load directly:

```bash
# Từ Neo4j Browser, import file
# From Neo4j Browser, import file
:load impl/kgraph/full.cypher
```

#### Bước 3: Chạy Java Knowledge Graph Creator / Run Java Knowledge Graph Creator

```bash
cd impl
javac -cp ".:path/to/neo4j-driver.jar" main.java
# Note: This attempts to run an inner class defined in main.java
# The actual structure is: NavalCloudElaborationDemo class contains NavalKnowledgeGraph as inner class
java -cp ".:path/to/neo4j-driver.jar" NavalCloudElaborationDemo\$NavalKnowledgeGraph
```

**Lưu ý / Note**: Đảm bảo Neo4j đang chạy và cấu hình đúng thông tin đăng nhập / Ensure Neo4j is running and credentials are properly configured.

### 4. Chạy CLIPS Rules / Running CLIPS Rules

```bash
cd impl/rules

# Khởi động CLIPS và load rules
# Start CLIPS and load rules
clips

# Trong CLIPS prompt / In CLIPS prompt:
(load "main.clp")
(reset)
(run)
```

Hoặc chạy trực tiếp / Or run directly:

```bash
clips -f main.clp
```

### 5. Các ví dụ khác / Other Examples

#### Case-Based Reasoning

```bash
cd impl/case
javac -cp "." casecode.java
java CaseBasedReasoning
```

#### Ontology Processing

```bash
cd impl/onto
# Xem ontology definitions
# View ontology definitions
cat ontocode.on
```

## Cấu trúc dự án / Project Structure

```
keraia/
├── impl/                      # Implementations
│   ├── main.java             # Main Java demo (Naval Cloud Elaboration)
│   ├── case/                 # Case-Based Reasoning implementations
│   ├── causal/               # Causal reasoning (Python)
│   │   ├── main.py           # Main causal reasoning demo
│   │   └── causalcode.py     # Causal reasoning code
│   ├── keraia/               # Core KERAIA implementations
│   │   └── keraiacode.java   # Core KERAIA Java code
│   ├── kgraph/               # Knowledge Graph (Neo4j)
│   │   ├── full.cypher       # Complete graph queries
│   │   └── graphcode.cy      # Graph code
│   ├── onto/                 # Ontology definitions
│   │   ├── ontocode.on       # Ontology code
│   │   └── fullset.on        # Full ontology set
│   └── rules/                # Rule-based reasoning (CLIPS)
│       ├── main.clp          # Main CLIPS rules
│       └── rulescode.clp     # Rules code
├── analysis/                  # Analysis files
├── appendices/               # Appendices
├── cypherrules/              # Cypher rules
├── images/                   # Images
├── klines/                   # K-Lines
├── ksynth/                   # K-Synth
├── logs/                     # Log files
├── rulegui/                  # Rule GUI
├── transformations/          # Transformations
├── watertreatment/           # Water treatment use case
├── amendments.md             # Amendments documentation
├── SKIMA_Journal_V2.pdf      # Research paper
└── README.md                 # This file
```

## Ví dụ sử dụng / Usage Examples

### Ví dụ 1: Naval Threat Detection / Example 1: Naval Threat Detection

Chương trình demo trong `impl/main.java` mô phỏng việc xử lý các nguồn tri thức trong kịch bản hải quân:

```java
// Cloud A: Initial knowledge sources
KS_TR1: Sonar detection - possible submarine contact
KS_TR2: Radar detection - unidentified vessel
KS_SF3: Threat confidence level: 50.0

// After elaboration -> Cloud B:
KS_TR1: Enhanced detection from sonar
KS_TR2: Refined radar classification
KS_SF3: Computed threat probability: 65.0
```

### Ví dụ 2: Causal Reasoning / Example 2: Causal Reasoning

Python implementation trong `impl/causal/main.py`:

```python
# Defines causal relationships between naval knowledge sources
# Performs Bayesian inference
# Generates probabilistic predictions
```

### Ví dụ 3: Knowledge Graph Queries / Example 3: Knowledge Graph Queries

Cypher queries trong Neo4j:

```cypher
// Find all knowledge sources connected to threat assessment
MATCH (ks:KnowledgeSource)-[:DERIVES|ANALYZES*]->(threat)
WHERE threat.name CONTAINS 'THREAT'
RETURN ks, threat
```

## Xử lý sự cố / Troubleshooting

### Lỗi Java Compilation / Java Compilation Errors

**Vấn đề / Problem**: Không tìm thấy các class dependencies
**Giải pháp / Solution**: Đảm bảo tất cả JAR files cần thiết có trong classpath

### Lỗi Python Import / Python Import Errors

**Vấn đề / Problem**: `ModuleNotFoundError`
**Giải pháp / Solution**: 
```bash
pip install --upgrade numpy networkx dowhy pandas
```

### Lỗi Neo4j Connection / Neo4j Connection Errors

**Vấn đề / Problem**: Không thể kết nối đến Neo4j
**Giải pháp / Solution**:
1. Đảm bảo Neo4j đang chạy / Ensure Neo4j is running
2. Kiểm tra URI, username và password trong code / Check URI, username and password in code
3. Mở firewall cho port 7687 / Open firewall for port 7687

### Lỗi CLIPS / CLIPS Errors

**Vấn đề / Problem**: CLIPS not found
**Giải pháp / Solution**: Cài đặt CLIPS theo hướng dẫn ở phần Prerequisites

## Đóng góp / Contributing

Contributions are welcome! Các đóng góp được hoan nghênh!

## Giấy phép / License

Xem file LICENSE để biết thêm chi tiết / See LICENSE file for details.

## Liên hệ / Contact

Để biết thêm thông tin, vui lòng tham khảo tài liệu `SKIMA_Journal_V2.pdf` hoặc `amendments.md`.

For more information, please refer to the `SKIMA_Journal_V2.pdf` document or `amendments.md`.

## Tài liệu tham khảo / References

- Apache Jena: https://jena.apache.org/
- Neo4j: https://neo4j.com/
- DoWhy (Causal Inference): https://microsoft.github.io/dowhy/
- CLIPS: https://www.clipsrules.net/
