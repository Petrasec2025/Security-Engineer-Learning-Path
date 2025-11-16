# SAST (Static Application Security Testing) - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![SAST](https://img.shields.io/badge/SAST-Static%20Analysis-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time](https://img.shields.io/badge/Time-30%20minutes-green)
![Category](https://img.shields.io/badge/Category-Software%20Security-purple)

## 📋 Room Overview

**Room Title:** SAST (Static Application Security Testing)  
**Platform:** TryHackMe  
**Category:** Software Security  
**Duration:** 30 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 4% (Partial Completion)

## 🎯 Learning Objectives

- **Manual Code Review** techniques and methodologies
- **SAST Tools** implementation and usage
- **False Positive/Negative** management
- **IDE Integration** of security tools
- **Development Lifecycle** integration strategies

## 🔍 Core Concepts & Definitions

### Task 2: Code Review

**Code Review Definition:** Process of examining source code to identify security vulnerabilities using white-box approach.

**Manual vs Automated Code Review:**

| Aspect | Manual Review | Automated Review |
|--------|---------------|------------------|
| **Speed** | Slower | Faster |
| **Thoroughness** | More thorough | Less thorough |
| **Cost** | Higher | Lower |
| **Consistency** | Variable | Consistent |
| **Coverage** | Limited by human capacity | Comprehensive |

**Key Insights:**
- Automated tools excel at finding common vulnerabilities quickly
- Manual reviews provide deeper analysis and context understanding
- Best approach: Combine both for comprehensive security assessment

**Answers:**
- Automated as substitute: `nay`
- Faster review: `Automated`
- More thorough: `Manual`

### Task 3: Manual Code Review

**Manual Review Process:**
1. **Identify Insecure Functions:** Search for potentially dangerous functions
2. **Understand Context:** Analyze how functions are used
3. **Trace User Inputs:** Follow data flow from sources to sinks

**Practical Exercise:**
- Target application: `/home/ubuntu/Desktop/simple-webapp/`
- Focus: SQL injection vulnerabilities in PHP/MySQL
- Tools used: `grep` for pattern searching

**SQL Injection Detection:**
```bash
# Search for MySQL query functions
grep -r -n 'mysqli_query('
grep -rn 'db_query('
```

**Key Vulnerabilities Found:**
1. **Direct SQL Injection:** `$_GET['guest_id']` concatenated without sanitization
2. **Filter Bypass:** `preg_replace()` with limited replacements allowing injection

**LFI Vulnerability Analysis:**
- **Vulnerable functions:** `require()`, `include()`, `require_once()`, `include_once()`
- **Detection:** Search for user-controlled input in include statements

**Answers:**
- LVI function used: `include()`
- Function instances: `9`
- Vulnerable file: `view.php`
- Vulnerable line: `22`

### Task 4: Automated Code Review

**SAST Definition:** Static Application Security Testing - automated tools for code analysis without executing the application.

**SAST Analysis Techniques:**

| Technique | Description | Example |
|-----------|-------------|---------|
| **Semantic Analysis** | Pattern matching for insecure functions | `grep`-like searching |
| **Dataflow Analysis** | Tracing data from sources to sinks | Taint analysis |
| **Control Flow Analysis** | Analyzing operation sequences | Race conditions |
| **Structural Analysis** | Code structure best practices | Dead code detection |
| **Configuration Analysis** | Application configuration checks | `php.ini` settings |

**SAST Pros & Cons:**

**Pros:**
- No running instance required
- Great code coverage
- Fast execution
- Exact vulnerability location reporting
- Easy CI/CD integration

**Cons:**
- Source code access required
- Prone to false positives
- Can't detect runtime vulnerabilities
- Language-specific limitations

**Answers:**
- Running instance required: `nay`
- Dead code detection: `structural analysis`
- Configuration flaws: `configuration analysis`
- Grep-like analysis: `semantic analysis`

### Task 5: SAST Tools - Psalm

**Psalm Tool:** PHP Static Analysis Linting Machine

**Key Features:**
- Structural analysis for coding best practices
- Taint analysis for security vulnerabilities
- Configurable error levels
- Annotation support for custom sinks

**Usage:**
```bash
# Basic analysis
./vendor/bin/psalm --no-cache

# Taint analysis
./vendor/bin/psalm --no-cache --taint-analysis
```

**Annotation Examples:**
```php
/**
 * @psalm-taint-sink sql $query
 * @psalm-taint-specialize
 */
function db_query($conn, $query){
    $result = mysqli_query($conn, $query);
    return $result;
}
```

**Error Types:**
- **False Positive:** Tool reports vulnerability that doesn't exist
- **False Negative:** Tool misses actual vulnerability

**Manual vs SAST Comparison:**
| Vulnerability | Manual | Psalm | Verdict |
|---------------|--------|-------|----------|
| `$sql` | Vulnerable | Vulnerable | OK |
| `$sql2` | Not Vulnerable | Vulnerable | False Positive |
| `$sql3` | Vulnerable | Not Vulnerable | False Negative |

**Answers:**
- Incorrect vulnerability report: `false positive`
- Errors after annotation: `9`

### Task 6: SAST in Development Cycle

**Integration Strategies:**

**CI/CD Integration:**
- Run SAST on pull requests/merges
- Prevent vulnerable code from merging
- Can cause pipeline slowdowns

**IDE Integration:**
- Real-time code analysis
- Immediate feedback for developers
- Early vulnerability detection

**Tools Used:**
- **Psalm:** PHP-specific SAST with IDE plugin
- **Semgrep:** Multi-language SAST with custom rules

**VS Code Integration:**
- Inline problem highlighting
- Hover information for details
- Problems panel for overview

**Practical Exercise - ReciPHP Analysis:**
- Project: Old version of ReciPHP app
- Tools: Semgrep in VS Code
- Findings: SQL injection and XSS vulnerabilities

**Answers:**
- Total Semgrep problems: `27`
- showrecipe.inc.php problems: `8`
- Additional problem identifier: `echoed-request`
- Vulnerability type: `cross-site scripting`

## 🛠️ Technical Implementation

### Manual Review Methodology
1. **Function Identification:** Search for dangerous functions
2. **Context Analysis:** Examine function usage patterns
3. **Data Flow Tracing:** Follow user input to vulnerable sinks
4. **Sanitization Verification:** Check input validation effectiveness

### SAST Tool Configuration
- **Error Levels:** Adjust sensitivity based on project needs
- **Custom Annotations:** Define project-specific sinks
- **Rule Customization:** Tailor analysis to application context
- **Integration Points:** IDE vs CI/CD based on workflow

### False Positive Management
- **Manual Verification:** Validate all SAST findings
- **Annotation Usage:** Provide context to tools
- **Rule Tuning:** Adjust analysis rules over time
- **Team Education:** Understand tool limitations

## 📈 Personal Reflection

This room provided excellent hands-on experience with both manual and automated code review techniques, highlighting the strengths and limitations of each approach.

**Key Technical Insights:**
- The importance of understanding code context beyond simple pattern matching
- How SAST tools use abstract syntax trees and dataflow analysis for comprehensive coverage
- The critical role of annotations in improving SAST tool accuracy
- The complementary nature of manual and automated review processes

**Practical Learning Outcomes:**
- Hands-on experience with Psalm for PHP code analysis
- Understanding of taint analysis and data flow tracking
- Skills in identifying and managing false positives/negatives
- Experience with IDE integration of security tools
- Knowledge of development lifecycle integration strategies

**Real-World Application:**
The skills gained directly apply to:
- Secure code development practices
- DevSecOps pipeline implementation
- Security tool selection and configuration
- Code review process optimization
- Vulnerability management programs

**Professional Development Value:**
This room is essential for:
- **Developers** implementing secure coding practices
- **Security Engineers** configuring SAST tools
- **DevOps Teams** integrating security into pipelines
- **Code Reviewers** performing security assessments
- **Security Managers** establishing code review processes

**Areas for Further Development:**
- Advanced SAST tool configuration and customization
- Multi-language SAST implementation
- SAST tool comparison and selection criteria
- Automated false positive reduction techniques
- SAST integration with other security testing tools

---

*This writeup documents my comprehensive learning journey through SAST principles and practical implementation, providing essential knowledge for integrating static analysis into modern software development workflows.*
