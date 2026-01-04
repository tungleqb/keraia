# KERAIA - Knowledge Engineering and Reference AI Architecture

## Tổng quan / Overview

KERAIA là một framework phát triển cho kỹ thuật tri thức tượng trưng (symbolic knowledge engineering) được thiết kế để giải quyết các thách thức về biểu diễn, lập luận và thực thi tri thức trong môi trường phức tạp và động.

KERAIA is a framework for symbolic knowledge engineering designed to address the challenges of representing, reasoning with, and executing knowledge in dynamic and complex environments.

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
- **Apache Jena**: Thư viện cho xử lý ontology / Library for ontology processing
- **Neo4j Java Driver**: Cho tương tác với knowledge graph / For knowledge graph interaction
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

#### Phương pháp 2: Sử dụng Maven / Method 2: Using Maven

Tạo file `pom.xml` trong thư mục `impl`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    
    <groupId>keraia</groupId>
    <artifactId>keraia-impl</artifactId>
    <version>1.0-SNAPSHOT</version>
    
    <properties>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
    </properties>
    
    <dependencies>
        <dependency>
            <groupId>org.apache.jena</groupId>
            <artifactId>apache-jena-libs</artifactId>
            <version>4.7.0</version>
            <type>pom</type>
        </dependency>
        <dependency>
            <groupId>org.neo4j.driver</groupId>
            <artifactId>neo4j-java-driver</artifactId>
            <version>5.5.0</version>
        </dependency>
    </dependencies>
</project>
```

Sau đó chạy / Then run:

```bash
cd impl
mvn compile
mvn exec:java -Dexec.mainClass="NavalCloudElaborationDemo"
```

#### Kết quả mong đợi / Expected Output

Chương trình sẽ hiển thị / The program will display:
- Cloud A: Các nguồn tri thức ban đầu / Initial knowledge sources
- Cloud B: Các tri thức đã được tinh chỉnh sau khi elaboration / Refined knowledge after elaboration
- Thông tin về sonar detection, radar detection, threat probability, fleet positioning, v.v. / Information about sonar detection, radar detection, threat probability, fleet positioning, etc.

### 2. Chạy Python Causal Reasoning Demo / Running Python Causal Reasoning Demo

```bash
cd impl/causal

# Chạy demo causal reasoning
# Run causal reasoning demo
python main.py
```

**Kết quả mong đợi / Expected Output**:
- Mô phỏng kịch bản hải quân với causal relationships / Naval scenario simulation with causal relationships
- Probabilistic dependencies giữa các knowledge sources / Probabilistic dependencies between knowledge sources
- Bayesian fusion và causal inference / Bayesian fusion and causal inference

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
java -cp ".:path/to/neo4j-driver.jar" NavalCloudElaborationDemo.NavalKnowledgeGraph
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
