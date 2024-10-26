# PRÁCTICA CI/CD
*Santiago Córdoba Herrera*

## 1. Fork del repositorio
Se realizó un fork del repositorio [base](https://github.com/leonjaramillo/protobootapp)

## 2. Integración Continua con Github Actions
Se utilizó el workflow *Java CI with Maven* que ya estaba creado desde el repositorio base
<div align="left"><img src="./docs/evidences/workflow.png" width="500"/></div>

### 2.1. Escenarios
#### a) Build tras commit a rama master
<div align="left"><img src="./docs/evidences/commit_master.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/build_after_commit.png" width="500"/></div>

#### b) Error en el build tras error en prueba unitaria
<div align="left"><img src="./docs/evidences/commit_fail_unit_test.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/build_failure_after_unit_test.png" width="500"/></div>

#### c) Error en el build tras error en prueba de integracion
<div align="left"><img src="./docs/evidences/commit_fail_integration_test.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/build_failure_after_integration_test.png" width="500"/></div>

#### b) Error por validación del estilo o formato
<div align="left"><img src="./docs/evidences/commit_change_checkstyle.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/build_failure_after_checkstyle_change.png" width="500"/></div>

## 3. Integración Continua con Jenkins
### 3.1. Escenarios
#### a) Error en el build tras error en prueba unitaria
Se aprovecha el mismo commit de Github Actions
<div align="left"><img src="./docs/evidences/commit_fail_unit_test.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/jenkins_failure_unit_test.png" width="500"/></div>

#### b) Error en el build tras error en prueba de integracion
Se aprovecha el mismo commit de Github Actions
<div align="left"><img src="./docs/evidences/commit_fail_integration_test.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/jenkins_failure_integration_test.png" width="500"/></div>

#### c) Error por validación del estilo o formato
Se aprovecha el mismo commit de Github Actions
<div align="left"><img src="./docs/evidences/commit_change_checkstyle.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/jenkins_failure_checkstyle.png" width="500"/></div>

#### d) Error por incumplimiento con el limite de Code Coverage
Se aprovecha el mismo commit de Github Actions
<div align="left"><img src="./docs/evidences/change_coverage_limit.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/jenkins_failure_coverage.png" width="500"/></div>

### 3.2. Visualización en Blue Ocean
<div align="left"><img src="./docs/evidences/blue_ocean.png" width="500"/></div>

## 4. Despliegue continuo con AWS
### 4.1. Creación de ambientes
<div align="left"><img src="./docs/evidences/entornos_beanstalk.png" width="500"/></div>

### 4.2. Escenarios
#### a) Error en el build tras error en prueba unitaria
<div align="left"><img src="./docs/evidences/aws_failure_unit_test.png" width="500"/></div>

#### b) Error en el build tras error en prueba de integracion
<div align="left"><img src="./docs/evidences/aws_failure_integration_test.png" width="500"/></div>

#### c) Error por validación del estilo o formato
<div align="left"><img src="./docs/evidences/aws_failure_checkstyle.png" width="500"/></div>

#### d) Error por incumplimiento con el limite de Code Coverage
<div align="left"><img src="./docs/evidences/aws_failure_coverage.png" width="500"/></div>

### 4.3. URLs Spring Boot Actuator
<div align="left"><img src="./docs/evidences/aws_actuator_info.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/aws_actuator_health.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/aws_actuator_metrics.png" width="500"/></div>

### 4.4. CloudWatch
<div align="left"><img src="./docs/evidences/aws_cloudwatch.png" width="500"/></div>
<div align="left"><img src="./docs/evidences/aws_cloudwatch_detalle.png" width="500"/></div>

### 4.5. Reportes CodeBuild
<div align="left"><img src="./docs/evidences/aws_reports.png" width="500"/></div>
