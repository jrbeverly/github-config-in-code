# FLOSS Best Practices

## Passing

### Basics

#### Basic project website content

- The project website MUST succinctly describe what the software does (what problem does it solve?). [description_good]
- The project website MUST provide information on how to: obtain, provide feedback (as bug reports or enhancements), and contribute to the software. [interact]
- The information on how to contribute MUST explain the contribution process (e.g., are pull requests used?) {Met URL} [contribution]
- The information on how to contribute SHOULD include the requirements for acceptable contributions (e.g., a reference to any required coding standard). {Met URL} [contribution_requirements]

#### FLOSS license

- The software produced by the project MUST be released as FLOSS. [floss_license]
- It is SUGGESTED that any required license(s) for the software produced by the project be approved by the Open Source Initiative (OSI). [floss_license_osi]
- The project MUST post the license(s) of its results in a standard location in their source repository. {Met URL} [license_location]

#### Documentation

- The project MUST provide basic documentation for the software produced by the project. {N/A justification} [documentation_basics]
- The project MUST provide reference documentation that describes the external interface (both input and output) of the software produced by the project. {N/A justification} [documentation_interface]

#### Other

- The project sites (website, repository, and download URLs) MUST support HTTPS using TLS. [sites_https]
- The project MUST have one or more mechanisms for discussion (including proposed changes and issues) that are searchable, allow messages and topics to be addressed by URL, enable new people to participate in some of the discussions, and do not require client-side installation of proprietary software. [discussion]
- The project SHOULD provide documentation in English and be able to accept bug reports and comments about code in English. [english]
- The project MUST be maintained. [maintained]

### Change Control

#### Public version-controlled source repository

- The project MUST have a version-controlled source repository that is publicly readable and has a URL. [repo_public]
- The project's source repository MUST track what changes were made, who made the changes, and when the changes were made. [repo_track]
- To enable collaborative review, the project's source repository MUST include interim versions for review between releases; it MUST NOT include only final releases. [repo_interim]
- It is SUGGESTED that common distributed version control software be used (e.g., git) for the project's source repository. [repo_distributed]

#### Unique version numbering

- The project results MUST have a unique version identifier for each release intended to be used by users. [version_unique]
- It is SUGGESTED that the Semantic Versioning (SemVer) or Calendar Versioning (CalVer) version numbering format be used for releases. It is SUGGESTED that those who use CalVer include a micro level value. [version_semver]
- It is SUGGESTED that projects identify each release within their version control system. For example, it is SUGGESTED that those using git identify each release using git tags. [version_tags]

#### Release notes

- The project MUST provide, in each release, release notes that are a human-readable summary of major changes in that release to help users determine if they should upgrade and what the upgrade impact will be. The release notes MUST NOT be the raw output of a version control log (e.g., the "git log" command results are not release notes). Projects whose results are not intended for reuse in multiple locations (such as the software for a single website or service) AND employ continuous delivery MAY select "N/A". {N/A justification} {Met URL} [release_notes]
- The release notes MUST identify every publicly known run-time vulnerability fixed in this release that already had a CVE assignment or similar when the release was created. This criterion may be marked as not applicable (N/A) if users typically cannot practically update the software themselves (e.g., as is often true for kernel updates). This criterion applies only to the project results, not to its dependencies. If there are no release notes or there have been no publicly known vulnerabilities, choose N/A. {N/A justification} [release_notes_vulns]

### Reporting

#### Bug-reporting process

- The project MUST provide a process for users to submit bug reports (e.g., using an issue tracker or a mailing list). {Met URL} [report_process]
- The project SHOULD use an issue tracker for tracking individual issues. [report_tracker]
- The project MUST acknowledge a majority of bug reports submitted in the last 2-12 months (inclusive); the response need not include a fix. [report_responses]
- The project SHOULD respond to a majority (>50%) of enhancement requests in the last 2-12 months (inclusive). [enhancement_responses]
- The project MUST have a publicly available archive for reports and responses for later searching. {Met URL} [report_archive]

#### Vulnerability report process

- The project MUST publish the process for reporting vulnerabilities on the project site. {Met URL} [vulnerability_report_process]
- If private vulnerability reports are supported, the project MUST include how to send the information in a way that is kept private. {N/A allowed} {Met URL} [vulnerability_report_private]
- The project's initial response time for any vulnerability report received in the last 6 months MUST be less than or equal to 14 days. {N/A allowed} [vulnerability_report_response]

#### Quality

#### Working build system

- If the software produced by the project requires building for use, the project MUST provide a working build system that can automatically rebuild the software from source code. {N/A allowed} [build]
- It is SUGGESTED that common tools be used for building the software. {N/A allowed} [build_common_tools]
- The project SHOULD be buildable using only FLOSS tools. {N/A allowed} [build_floss_tools]

#### Automated test suite

- The project MUST use at least one automated test suite that is publicly released as FLOSS (this test suite may be maintained as a separate FLOSS project). The project MUST clearly show or document how to run the test suite(s) (e.g., via a continuous integration (CI) script or via documentation in files such as BUILD.md, README.md, or CONTRIBUTING.md). [test]
- A test suite SHOULD be invocable in a standard way for that language. [test_invocation]
- It is SUGGESTED that the test suite cover most (or ideally all) the code branches, input fields, and functionality. [test_most]
- It is SUGGESTED that the project implement continuous integration (where new or changed code is frequently integrated into a central code repository and automated tests are run on the result). [test_continuous_integration]

#### New functionality testing

- The project MUST have a general policy (formal or not) that as major new functionality is added to the software produced by the project, tests of that functionality should be added to an automated test suite. [test_policy]
- The project MUST have evidence that the test_policy for adding tests has been adhered to in the most recent major changes to the software produced by the project. [tests_are_added]
- It is SUGGESTED that this policy on adding tests (see test_policy) be documented in the instructions for change proposals. [tests_documented_added]

#### Warning flags

- The project MUST enable one or more compiler warning flags, a "safe" language mode, or use a separate "linter" tool to look for code quality errors or common simple mistakes, if there is at least one FLOSS tool that can implement this criterion in the selected language. {N/A allowed} [warnings]
- The project MUST address warnings. {N/A allowed} [warnings_fixed]
- It is SUGGESTED that projects be maximally strict with warnings in the software produced by the project, where practical. {N/A allowed} [warnings_strict]

### Security

#### Secure development knowledge

- The project MUST have at least one primary developer who knows how to design secure software. (See ???details??? for the exact requirements.) [know_secure_design]
- At least one of the project's primary developers MUST know of common kinds of errors that lead to vulnerabilities in this kind of software, as well as at least one method to counter or mitigate each of them. [know_common_errors]

#### Use basic good cryptographic practices

- The software produced by the project MUST use, by default, only cryptographic protocols and algorithms that are publicly published and reviewed by experts (if cryptographic protocols and algorithms are used). {N/A allowed} [crypto_published]
- If the software produced by the project is an application or library, and its primary purpose is not to implement cryptography, then it SHOULD only call on software specifically designed to implement cryptographic functions; it SHOULD NOT re-implement its own. {N/A allowed} [crypto_call]
- All functionality in the software produced by the project that depends on cryptography MUST be implementable using FLOSS. {N/A allowed} [crypto_floss]
- The security mechanisms within the software produced by the project MUST use default keylengths that at least meet the NIST minimum requirements through the year 2030 (as stated in 2012). It MUST be possible to configure the software so that smaller keylengths are completely disabled. {N/A allowed} [crypto_keylength]
- The default security mechanisms within the software produced by the project MUST NOT depend on broken cryptographic algorithms (e.g., MD4, MD5, single DES, RC4, Dual_EC_DRBG), or use cipher modes that are inappropriate to the context, unless they are necessary to implement an interoperable protocol (where the protocol implemented is the most recent version of that standard broadly supported by the network ecosystem, that ecosystem requires the use of such an algorithm or mode, and that ecosystem does not offer any more secure alternative). The documentation MUST describe any relevant security risks and any known mitigations if these broken algorithms or modes are necessary for an interoperable protocol. {N/A allowed} [crypto_working]
- The default security mechanisms within the software produced by the project SHOULD NOT depend on cryptographic algorithms or modes with known serious weaknesses (e.g., the SHA-1 cryptographic hash algorithm or the CBC mode in SSH). {N/A allowed} [crypto_weaknesses]
- The security mechanisms within the software produced by the project SHOULD implement perfect forward secrecy for key agreement protocols so a session key derived from a set of long-term keys cannot be compromised if one of the long-term keys is compromised in the future. {N/A allowed} [crypto_pfs]
- If the software produced by the project causes the storing of passwords for authentication of external users, the passwords MUST be stored as iterated hashes with a per-user salt by using a key stretching (iterated) algorithm (e.g., Argon2id, Bcrypt, Scrypt, or PBKDF2). See also OWASP Password Storage Cheat Sheet). {N/A allowed} [crypto_password_storage]
- The security mechanisms within the software produced by the project MUST generate all cryptographic keys and nonces using a cryptographically secure random number generator, and MUST NOT do so using generators that are cryptographically insecure. {N/A allowed} [crypto_random]

#### Secured delivery against man-in-the-middle (MITM) attacks

- The project MUST use a delivery mechanism that counters MITM attacks. Using https or ssh+scp is acceptable. [delivery_mitm]
- A cryptographic hash (e.g., a sha1sum) MUST NOT be retrieved over http and used without checking for a cryptographic signature. [delivery_unsigned]

#### Publicly known vulnerabilities fixed

- There MUST be no unpatched vulnerabilities of medium or higher severity that have been publicly known for more than 60 days. [vulnerabilities_fixed_60_days]
- Projects SHOULD fix all critical vulnerabilities rapidly after they are reported. [vulnerabilities_critical_fixed]

#### Other security issues

- The public repositories MUST NOT leak a valid private credential (e.g., a working password or private key) that is intended to limit public access. [no_leaked_credentials]

### Analysis

#### Static code analysis

- At least one static code analysis tool (beyond compiler warnings and "safe" language modes) MUST be applied to any proposed major production release of the software before its release, if there is at least one FLOSS tool that implements this criterion in the selected language. {N/A justification} {Met justification} [static_analysis]
- It is SUGGESTED that at least one of the static analysis tools used for the static_analysis criterion include rules or approaches to look for common vulnerabilities in the analyzed language or environment. {N/A allowed} [static_analysis_common_vulnerabilities]
- All medium and higher severity exploitable vulnerabilities discovered with static code analysis MUST be fixed in a timely way after they are confirmed. {N/A allowed} [static_analysis_fixed]
- It is SUGGESTED that static source code analysis occur on every commit or at least daily. {N/A allowed} [static_analysis_often]

#### Dynamic code analysis

- It is SUGGESTED that at least one dynamic analysis tool be applied to any proposed major production release of the software before its release. [dynamic_analysis]
- It is SUGGESTED that if the software produced by the project includes software written using a memory-unsafe language (e.g., C or C++), then at least one dynamic tool (e.g., a fuzzer or web application scanner) be routinely used in combination with a mechanism to detect memory safety problems such as buffer overwrites. If the project does not produce software written in a memory-unsafe language, choose "not applicable" (N/A). {N/A allowed} [dynamic_analysis_unsafe]
- It is SUGGESTED that the project use a configuration for at least some dynamic analysis (such as testing or fuzzing) which enables many assertions. In many cases these assertions should not be enabled in production builds. [dynamic_analysis_enable_assertions]
- All medium and higher severity exploitable vulnerabilities discovered with dynamic code analysis MUST be fixed in a timely way after they are confirmed. {N/A allowed} [dynamic_analysis_fixed]

## Silver

### Basics

#### Prerequisites

- The project MUST achieve a passing level badge. [achieve_passing]

#### Basic project website content

- The information on how to contribute MUST include the requirements for acceptable contributions (e.g., a reference to any required coding standard). {Met URL} [contribution_requirements]

#### Project oversight

- The project SHOULD have a legal mechanism where all developers of non-trivial amounts of project software assert that they are legally authorized to make these contributions. The most common and easily-implemented approach for doing this is by using a Developer Certificate of Origin (DCO), where users add "signed-off-by" in their commits and the project links to the DCO website. However, this MAY be implemented as a Contributor License Agreement (CLA), or other legal mechanism. {Met URL} [dco]
- The project MUST clearly define and document its project governance model (the way it makes decisions, including key roles). {Met URL} [governance]
- The project MUST adopt a code of conduct and post it in a standard location. {Met URL} [code_of_conduct]
- The project MUST clearly define and publicly document the key roles in the project and their responsibilities, including any tasks those roles must perform. It MUST be clear who has which role(s), though this might not be documented in the same way. {Met URL} [roles_responsibilities]
- The project MUST be able to continue with minimal interruption if any one person dies, is incapacitated, or is otherwise unable or unwilling to continue support of the project. In particular, the project MUST be able to create and close issues, accept proposed changes, and release versions of software, within a week of confirmation of the loss of support from any one individual. This MAY be done by ensuring someone else has any necessary keys, passwords, and legal rights to continue the project. Individuals who run a FLOSS project MAY do this by providing keys in a lockbox and a will providing any needed legal rights (e.g., for DNS names). {Met URL} [access_continuity]
- The project SHOULD have a "bus factor" of 2 or more. {Met URL} [bus_factor]

#### Documentation

- The project MUST have a documented roadmap that describes what the project intends to do and not do for at least the next year. {Met URL} [documentation_roadmap]
- The project MUST include documentation of the architecture (aka high-level design) of the software produced by the project. If the project does not produce software, select "not applicable" (N/A). {N/A justification} {Met URL} [documentation_architecture]
- The project MUST document what the user can and cannot expect in terms of security from the software produced by the project (its "security requirements"). {Met URL} [documentation_security]
- The project MUST provide a "quick start" guide for new users to help them quickly do something with the software. {N/A justification} {Met URL} [documentation_quick_start]
- The project MUST make an effort to keep the documentation consistent with the current version of the project results (including software produced by the project). Any known documentation defects making it inconsistent MUST be fixed. If the documentation is generally current, but erroneously includes some older information that is no longer true, just treat that as a defect, then track and fix as usual. {N/A justification} {Met justification} [documentation_current]
- The project repository front page and/or website MUST identify and hyperlink to any achievements, including this best practices badge, within 48 hours of public recognition that the achievement has been attained. {Met URL} [documentation_achievements]

#### Accessibility and internationalization

- The project (both project sites and project results) SHOULD follow accessibility best practices so that persons with disabilities can still participate in the project and use the project results where it is reasonable to do so. {N/A justification} {Met justification} [accessibility_best_practices]
- The software produced by the project SHOULD be internationalized to enable easy localization for the target audience's culture, region, or language. If internationalization (i18n) does not apply (e.g., the software doesn't generate text intended for end-users and doesn't sort human-readable text), select "not applicable" (N/A). {N/A justification} {Met justification} [internationalization]

#### Other

- If the project sites (website, repository, and download URLs) store passwords for authentication of external users, the passwords MUST be stored as iterated hashes with a per-user salt by using a key stretching (iterated) algorithm (e.g., Argon2id, Bcrypt, Scrypt, or PBKDF2). If the project sites do not store passwords for this purpose, select "not applicable" (N/A). {N/A justification} {Met justification} [sites_password_security]

### Change Control

#### Previous versions

- The project MUST maintain the most often used older versions of the product or provide an upgrade path to newer versions. If the upgrade path is difficult, the project MUST document how to perform the upgrade (e.g., the interfaces that have changed and detailed suggested steps to help upgrade). {N/A justification} {Met justification} [maintenance_or_update]

### Reporting

#### Bug-reporting process

The project MUST use an issue tracker for tracking individual issues. {N/A justification} {Met justification} [report_tracker]

#### Vulnerability report process

- The project MUST give credit to the reporter(s) of all vulnerability reports resolved in the last 12 months, except for the reporter(s) who request anonymity. If there have been no vulnerabilities resolved in the last 12 months, select "not applicable" (N/A). {N/A justification} {Met URL} [vulnerability_report_credit]
- The project MUST have a documented process for responding to vulnerability reports. {Met URL} [vulnerability_response_process]

### Quality

#### Coding standards

- The project MUST identify the specific coding style guides for the primary languages it uses, and require that contributions generally comply with it. {N/A justification} {Met URL} [coding_standards]
- The project MUST automatically enforce its selected coding style(s) if there is at least one FLOSS tool that can do so in the selected language(s). {N/A justification} {Met justification} [coding_standards_enforced]

#### Working build system

- Build systems for native binaries MUST honor the relevant compiler and linker (environment) variables passed in to them (e.g., CC, CFLAGS, CXX, CXXFLAGS, and LDFLAGS) and pass them to compiler and linker invocations. A build system MAY extend them with additional flags; it MUST NOT simply replace provided values with its own. If no native binaries are being generated, select "not applicable" (N/A). {N/A justification} {Met justification} [build_standard_variables]
- The build and installation system SHOULD preserve debugging information if they are requested in the relevant flags (e.g., "install -s" is not used). If there is no build or installation system (e.g., typical JavaScript libraries), select "not applicable" (N/A). {N/A justification} {Met justification} [build_preserve_debug]
- The build system for the software produced by the project MUST NOT recursively build subdirectories if there are cross-dependencies in the subdirectories. If there is no build or installation system (e.g., typical JavaScript libraries), select "not applicable" (N/A). {N/A justification} {Met justification} [build_non_recursive]
- The project MUST be able to repeat the process of generating information from source files and get exactly the same bit-for-bit result. If no building occurs (e.g., scripting languages where the source code is used directly instead of being compiled), select "not applicable" (N/A). {N/A justification} {Met justification} [build_repeatable]

#### Installation system

- The project MUST provide a way to easily install and uninstall the software produced by the project using a commonly-used convention. {N/A justification} {Met justification} [installation_common]
- The installation system for end-users MUST honor standard conventions for selecting the location where built artifacts are written to at installation time. For example, if it installs files on a POSIX system it MUST honor the DESTDIR environment variable. If there is no installation system or no standard convention, select "not applicable" (N/A). {N/A justification} {Met justification} [installation_standard_variables]
- The project MUST provide a way for potential developers to quickly install all the project results and support environment necessary to make changes, including the tests and test environment. This MUST be performed with a commonly-used convention. {N/A justification} {Met justification} [installation_development_quick]

#### Externally-maintained components

- The project MUST list external dependencies in a computer-processable way. {N/A justification} {Met URL} [external_dependencies]
- Projects MUST monitor or periodically check their external dependencies (including convenience copies) to detect known vulnerabilities, and fix exploitable vulnerabilities or verify them as unexploitable. {N/A justification} {Met justification} [dependency_monitoring]
- The project MUST either:
  - make it easy to identify and update reused externally-maintained components; or
  - use the standard components provided by the system or programming language.
- Then, if a vulnerability is found in a reused component, it will be easy to update that component. {N/A justification} {Met justification} [updateable_reused_components]
- The project SHOULD avoid using deprecated or obsolete functions and APIs where FLOSS alternatives are available in the set of technology it uses (its "technology stack") and to a supermajority of the users the project supports (so that users have ready access to the alternative). {N/A justification} {Met justification} [interfaces_current]

#### Automated test suite

- An automated test suite MUST be applied on each check-in to a shared repository for at least one branch. This test suite MUST produce a report on test success or failure. {Met justification} [automated_integration_testing]
- The project MUST add regression tests to an automated test suite for at least 50% of the bugs fixed within the last six months. {N/A justification} {Met justification} [regression_tests_added50]
- The project MUST have FLOSS automated test suite(s) that provide at least 80% statement coverage if there is at least one FLOSS tool that can measure this criterion in the selected language. {N/A justification} {Met justification} [test_statement_coverage80]

#### New functionality testing

- The project MUST have a formal written policy that as major new functionality is added, tests for the new functionality MUST be added to an automated test suite. {N/A justification} {Met justification} [test_policy_mandated]
- The project MUST include, in its documented instructions for change proposals, the policy that tests are to be added for major new functionality. {N/A justification} {Met justification} [tests_documented_added]

#### Warning flags

- Projects MUST be maximally strict with warnings in the software produced by the project, where practical. {N/A justification} {Met justification} [warnings_strict]

### Security

#### Secure development knowledge

- The project MUST implement secure design principles (from "know_secure_design"), where applicable. If the project is not producing software, select "not applicable" (N/A). {N/A justification} {Met justification} [implement_secure_design]

#### Use basic good cryptographic practices

- The default security mechanisms within the software produced by the project MUST NOT depend on cryptographic algorithms or modes with known serious weaknesses (e.g., the SHA-1 cryptographic hash algorithm or the CBC mode in SSH). {N/A allowed} {Met justification} [crypto_weaknesses]
- The project SHOULD support multiple cryptographic algorithms, so users can quickly switch if one is broken. Common symmetric key algorithms include AES, Twofish, and Serpent. Common cryptographic hash algorithm alternatives include SHA-2 (including SHA-224, SHA-256, SHA-384 AND SHA-512) and SHA-3. {N/A allowed} {Met justification} [crypto_algorithm_agility]
- The project MUST support storing authentication credentials (such as passwords and dynamic tokens) and private cryptographic keys in files that are separate from other information (such as configuration files, databases, and logs), and permit users to update and replace them without code recompilation. If the project never processes authentication credentials and private cryptographic keys, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_credential_agility]
- The software produced by the project SHOULD support secure protocols for all of its network communications, such as SSHv2 or later, TLS1.2 or later (HTTPS), IPsec, SFTP, and SNMPv3. Insecure protocols such as FTP, HTTP, telnet, SSLv3 or earlier, and SSHv1 SHOULD be disabled by default, and only enabled if the user specifically configures it. If the software produced by the project does not support network communications, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_used_network]
- The software produced by the project SHOULD, if it supports or uses TLS, support at least TLS version 1.2. Note that the predecessor of TLS was called SSL. If the software does not use TLS, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_tls12]
- The software produced by the project MUST, if it supports TLS, perform TLS certificate verification by default when using TLS, including on subresources. If the software does not use TLS, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_certificate_verification]
- The software produced by the project MUST, if it supports TLS, perform certificate verification before sending HTTP headers with private information (such as secure cookies). If the software does not use TLS, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_verification_private]

#### Secure release

- The project MUST cryptographically sign releases of the project results intended for widespread use, and there MUST be a documented process explaining to users how they can obtain the public signing keys and verify the signature(s). The private key for these signature(s) MUST NOT be on site(s) used to directly distribute the software to the public. If releases are not intended for widespread use, select "not applicable" (N/A). {N/A justification} {Met justification} [signed_releases]
- It is SUGGESTED that in the version control system, each important version tag (a tag that is part of a major release, minor release, or fixes publicly noted vulnerabilities) be cryptographically signed and verifiable as described in signed_releases. {Met justification} [version_tags_signed]

#### Other security issues

- The project results MUST check all inputs from potentially untrusted sources to ensure they are valid (an *allowlist*), and reject invalid inputs, if there are any restrictions on the data at all. {N/A justification} {Met justification} [input_validation]
- Hardening mechanisms SHOULD be used in the software produced by the project so that software defects are less likely to result in security vulnerabilities. {N/A justification} {Met justification} [hardening]
- The project MUST provide an assurance case that justifies why its security requirements are met. The assurance case MUST include: a description of the threat model, clear identification of trust boundaries, an argument that secure design principles have been applied, and an argument that common implementation security weaknesses have been countered. {Met URL} [assurance_case]

### Analysis

#### Static code analysis

- The project MUST use at least one static analysis tool with rules or approaches to look for common vulnerabilities in the analyzed language or environment, if there is at least one FLOSS tool that can implement this criterion in the selected language. {N/A justification} {Met justification} [static_analysis_common_vulnerabilities]

#### Dynamic code analysis

- If the software produced by the project includes software written using a memory-unsafe language (e.g., C or C++), then at least one dynamic tool (e.g., a fuzzer or web application scanner) MUST be routinely used in combination with a mechanism to detect memory safety problems such as buffer overwrites. If the project does not produce software written in a memory-unsafe language, choose "not applicable" (N/A). {N/A justification} {Met justification} [dynamic_analysis_unsafe]

## Gold

### Basics

#### Prerequisites

- The project MUST achieve a silver level badge. [achieve_silver]

#### Project oversight

- The project MUST have a "bus factor" of 2 or more. {Met URL} [bus_factor]
- The project MUST have at least two unassociated significant contributors. {Met URL} [contributors_unassociated]

#### Other

- The project MUST include a copyright statement in each source file, identifying the copyright holder (e.g., the [project name] contributors). {Met justification} [copyright_per_file]
- The project MUST include a license statement in each source file. This MAY be done by including the following inside a comment near the beginning of each file: SPDX-License-Identifier: [SPDX license expression for project]. {Met justification} [license_per_file]

### Change Control

#### Public version-controlled source repository

- The project's source repository MUST use a common distributed version control software (e.g., git or mercurial). {Met justification} [repo_distributed]
- The project MUST clearly identify small tasks that can be performed by new or casual contributors. {Met URL} [small_tasks]
- The project MUST require two-factor authentication (2FA) for developers for changing a central repository or accessing sensitive data (such as private vulnerability reports). This 2FA mechanism MAY use mechanisms without cryptographic mechanisms such as SMS, though that is not recommended. {Met justification} [require_2FA]
- The project's two-factor authentication (2FA) SHOULD use cryptographic mechanisms to prevent impersonation. Short Message Service (SMS) based 2FA, by itself, does NOT meet this criterion, since it is not encrypted. {Met justification} [secure_2FA]

### Quality

#### Coding standards

- The project MUST document its code review requirements, including how code review is conducted, what must be checked, and what is required to be acceptable. {N/A justification} {Met URL} [code_review_standards]
- The project MUST have at least 50% of all proposed modifications reviewed before release by a person other than the author, to determine if it is a worthwhile modification and free of known issues which would argue against its inclusion {Met justification} [two_person_review]

#### Working build system

- The project MUST have a reproducible build. If no building occurs (e.g., scripting languages where the source code is used directly instead of being compiled), select "not applicable" (N/A). {N/A justification} {Met URL} [build_reproducible]

#### Automated test suite

- A test suite MUST be invocable in a standard way for that language. {Met URL} [test_invocation]
- The project MUST implement continuous integration, where new or changed code is frequently integrated into a central code repository and automated tests are run on the result. {Met URL} [test_continuous_integration]
- The project MUST have FLOSS automated test suite(s) that provide at least 90% statement coverage if there is at least one FLOSS tool that can measure this criterion in the selected language. {N/A justification} {Met justification} [test_statement_coverage90]
- The project MUST have FLOSS automated test suite(s) that provide at least 80% branch coverage if there is at least one FLOSS tool that can measure this criterion in the selected language. {N/A justification} {Met justification} [test_branch_coverage80]

### Security

#### Use basic good cryptographic practices

- The software produced by the project MUST support secure protocols for all of its network communications, such as SSHv2 or later, TLS1.2 or later (HTTPS), IPsec, SFTP, and SNMPv3. Insecure protocols such as FTP, HTTP, telnet, SSLv3 or earlier, and SSHv1 MUST be disabled by default, and only enabled if the user specifically configures it. If the software produced by the project does not support network communications, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_used_network]
- The software produced by the project MUST, if it supports or uses TLS, support at least TLS version 1.2. Note that the predecessor of TLS was called SSL. If the software does not use TLS, select "not applicable" (N/A). {N/A allowed} {Met justification} [crypto_tls12]

#### Secured delivery against man-in-the-middle (MITM) attacks

- The project website, repository (if accessible via the web), and download site (if separate) MUST include key hardening headers with nonpermissive values. {Met URL} [hardened_site]

#### Other security issues

- The project MUST have performed a security review within the last 5 years. This review MUST consider the security requirements and security boundary. {Met justification} [security_review]
- Hardening mechanisms MUST be used in the software produced by the project so that software defects are less likely to result in security vulnerabilities. {N/A justification} {Met URL} [hardening]

### Analysis

#### Dynamic code analysis

- The project MUST apply at least one dynamic analysis tool to any proposed major production release of the software produced by the project before its release. {N/A justification} {Met justification} [dynamic_analysis]
- The project SHOULD include many run-time assertions in the software it produces and check those assertions during dynamic analysis. {N/A justification} {Met justification} [dynamic_analysis_enable_assertions]