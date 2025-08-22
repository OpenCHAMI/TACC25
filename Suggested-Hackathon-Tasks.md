# 🛠️ Suggested Hackathon Topics

The following candidate topics are drawn from the backlog document and roadmap issues.  
They are scoped to fit within a two-hour hackathon and have **clear deliverables**.  
TSC members can use this list as a starting point and adapt or combine ideas as needed.

---

## 📋 Task List

| **Topic** | **Why It’s Suitable** | **Suggested Deliverables** |
|-----------|------------------------|-----------------------------|
| **Create an org-level build workflow template** | The backlog calls for reusable GitHub Actions workflows to standardise builds across repos. Teams can implement a basic `go-build-release.yml` template and integrate it into one repository during the hackathon. | - `.github/workflows/go-build-release.yml` file in one microservice repo <br> - Documentation describing usage <br> - PR ready for review |
| **Implement mandatory PR build workflow** | Consistency in CI is critical. A PR build workflow that runs tests without triggering releases meets this need. | - A GitHub workflow file that triggers on PRs but skips production tagging <br> - Tested on one repository <br> - Demonstration of passing CI checks |
| **Standardise Go versions** | Ensuring all repos use the same Go version improves reproducibility. A two-hour sprint can audit a few repos and update their `go-version` fields. | - Report or set of PRs showing updated `go-version` in CI configs <br> - A script to scan other repos |
| **Automate release PRs and Slack notifications** | Release automation encourages timely and predictable releases. Teams can build a minimal GitHub Action that opens a PR in the release repo when a tag is pushed and posts to Slack. | - Working action configured on a test repository <br> - Demonstration of a PR created <br> - Slack message (mocked if necessary) |
| **Implement CODEOWNERS and branch protection** | Improving governance is a high priority. Setting up CODEOWNERS and branch protection across one or two repositories is manageable within two hours. | - Draft CODEOWNERS file <br> - Updated branch protection rules <br> - Documentation or checklist for rollout |
| **Prototype a Go-based image-builder** | The image-builder rewrite is a large task, but a two-hour sprint could produce a minimal Go program that creates an OCI image with a kernel and initrd. | - Proof-of-concept Go program <br> - README explaining design decisions and next steps |
| **Audit roadmap issues and prioritise “low-hanging fruit”** | A script to categorise roadmap issues helps the TSC prioritise work. This can be done quickly with GitHub’s API. | - Report grouping issues by area (architecture, CI/CD, docs) <br> - Labels applied to issues <br> - Recommendations for follow-up |
| **Improve documentation for workflows** | Documentation is crucial to onboard new contributors. Participants can draft instructions on how to consume the new org-level workflows and propose publication. | - Markdown doc explaining workflow usage <br> - PR adding it to a repository <br> - Review feedback |
| **Design a basic ClusterAPI provider** | RFD #68 proposes a ClusterAPI provider for OpenCHAMI. A hackathon team could outline the API schema and produce a simple controller skeleton. | - API design document <br> - Scaffolded Go code using kubebuilder <br> - Roadmap for further development |
| **Create a remote console service skeleton** | RFD #67 calls for a remote console service. A prototype exposing basic endpoints and integrating with OPAAL’s auth could be started. | - Minimal API with login & session endpoints <br> - Notes on BMC protocol integration <br> - Dependency list |
| **Draft a power control API** | RFD #54 proposes a simplified power control API. This can be prototyped quickly using SMD’s existing inventory data. | - Go or Python script exposing `/power/on` and `/power/off` endpoints <br> - Integration tests against mock inventory <br> - Documentation |
| **RPM Naming Conventions** | Address ongoing conflicts in RPM naming that cause installation issues and confusion. Alex has proposed clearer naming for services as we approach the 1.0 release milestone. | - Validate the proposal <br> - Implement naming updates across repos <br> - Ensure consistency in documentation and packaging |

---

## 📦 RPM Naming Proposal

As highlighted by Alex, the following new names are suggested:

- **SMD → OpenCHAMI-Inventory-Service**  
- **BSS → OpenCHAMI-Boot-Service**  
- **Power-control → OpenCHAMI-Power-Service**  
- **Remote-console → OpenCHAMI-Console-Service**  
- **Cloud-init → HPC-Metadata-Service**  
- **CoreSMD (DHCP) → OpenCHAMI-DHCP-Service**  
- **CoreSMD (DNS) → OpenCHAMI-DNS-Service**  
- **Magellan → HPC-Discovery-Tool**  
- **Image-builder → Imagesmith**  

Hackathon teams can validate this proposal, implement naming updates across repositories, and ensure consistency in docs and packaging.

---

## 🎯 Closing Note
These topics are intentionally varied — some are **code-oriented**, while others focus on **documentation** or **governance**.  
The TSC should select a **mix that engages participants of different skill sets** and yields tangible contributions.
