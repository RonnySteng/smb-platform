# SMB Platform

A multi-tenant, configurable platform for photo studios, plumbers, and electrical contractors.

## Overview

**SMB Platform** is a single codebase that adapts to different service industries through configuration, not custom code. The same system powers photography studios, plumbing companies, and electrical contractors without any industry-specific hardcoding.

## Key Features

- **Multi-Tenant Architecture**: Complete data isolation with support for unlimited companies
- - **Configurable Fields & Forms**: No developer needed to adapt the system
  - - **Role-Based Access Control**: Employee → Leader → Admin hierarchy
    - - **Job & Project Management**: Work order tracking with status history
      - - **Time Tracking**: Start/stop or manual entry with leader approval
        - - **Equipment & Inventory**: Asset management with loan workflows
          - - **Job Reporting**: Customizable reports with images
            - - **Quotes & Conversion**: Create and convert quotes to jobs
              - - **Export Ready**: CSV and PDF export functionality
               
                - ## Supported Industries
               
                - - **Photography**: Equipment management, delivery formats, client approvals
                  - - **Plumbing**: Pressure testing, materials tracking, inspection compliance
                    - - **Electrical**: Measurements, compliance certificates, inspection documentation
                     
                      - ## Core Modules
                     
                      - 1. **Users, Roles & Access**: Multi-role support with hierarchy management
                        2. 2. **Customers & Sites**: Company/private customers with multiple work sites
                           3. 3. **Jobs & Projects**: Work orders with configurable status workflows
                              4. 4. **Quotes**: Line items with quote-to-job conversion
                                 5. 5. **Time Tracking**: Per-user, per-job tracking with approvals
                                    6. 6. **Job Reports**: Text notes and image attachments with mandatory fields
                                       7. 7. **Equipment & Inventory**: Multi-level asset management with loan workflows
                                          8. 8. **Configuration Layer**: Custom fields, forms, and dashboards without code
                                            
                                             9. ## Equipment & Loan System
                                            
                                             10. ### Asset Levels
                                             11. - **Level 3**: Individual assets (serial numbers, instance-based)
                                                 - - **Level 2 & 1**: Stock-based assets (counted quantities)
                                                  
                                                   - ### Loan Workflow
                                                   - 1. Employee requests loan with condition confirmation
                                                     2. 2. System sends email confirmation
                                                        3. 3. Employee acknowledges receipt
                                                           4. 4. Asset marked "on_loan"
                                                              5. 5. Employee returns asset with condition report
                                                                 6. 6. Leader/admin confirms return
                                                                    7. 7. Email confirmation sent to employee
                                                                      
                                                                       8. ### Reports Required
                                                                       9. - My Loans (per user)
                                                                          - - Team Loans (per leader)
                                                                            - - All Loans (admin)
                                                                              - - Service Cases (admin)
                                                                                - - Assets Longest on Loan (admin)
                                                                                 
                                                                                  - ## Configuration Layer
                                                                                 
                                                                                  - Admins can configure without code:
                                                                                  - - Custom fields (text, number, date, select, multiselect, boolean, file, signature)
                                                                                    - - Form layouts (field ordering, sections, visibility)
                                                                                      - - Status workflows (allowed transitions)
                                                                                        - - Dashboard views (role-based)
                                                                                          - - Field-level role visibility
                                                                                            - - Mandatory field enforcement
                                                                                             
                                                                                              - ## Technology Stack
                                                                                             
                                                                                              - ### Backend
                                                                                              - - Node.js with Express or NestJS
                                                                                                - - PostgreSQL with multi-tenant schema
                                                                                                  - - Sequelize or TypeORM
                                                                                                    - - JWT authentication with tenant context
                                                                                                      - - S3 or MinIO for file storage
                                                                                                       
                                                                                                        - ### Frontend
                                                                                                        - - React with TypeScript
                                                                                                          - - TailwindCSS
                                                                                                            - - React Query
                                                                                                              - - React Hook Form
                                                                                                                - - Recharts
                                                                                                                 
                                                                                                                  - ### DevOps
                                                                                                                  - - Docker for containerization
                                                                                                                    - - GitHub Actions for CI/CD
                                                                                                                     
                                                                                                                      - ## Project Structure
                                                                                                                     
                                                                                                                      - ```
                                                                                                                        /src
                                                                                                                        ├── /core                 # Shared utilities, auth, database
                                                                                                                        ├── /domains             # Business logic (users, jobs, inventory, etc.)
                                                                                                                        ├── /config              # Custom fields, forms, dashboards
                                                                                                                        ├── /api                 # REST endpoints
                                                                                                                        ├── /ui                  # React frontend
                                                                                                                        └── /migrations          # Database migrations
                                                                                                                        ```
                                                                                                                        
                                                                                                                        ## Getting Started
                                                                                                                        
                                                                                                                        ### Prerequisites
                                                                                                                        - Node.js 18+
                                                                                                                        - - PostgreSQL 14+
                                                                                                                          - - npm or yarn
                                                                                                                           
                                                                                                                            - ### Installation
                                                                                                                           
                                                                                                                            - ```bash
                                                                                                                              git clone https://github.com/RonnySteng/smb-platform.git
                                                                                                                              cd smb-platform
                                                                                                                              npm install
                                                                                                                              cp .env.example .env
                                                                                                                              npm run migrate
                                                                                                                              npm run dev
                                                                                                                              ```
                                                                                                                              
                                                                                                                              ## Database Schema
                                                                                                                              
                                                                                                                              Uses PostgreSQL with `tenant_id` as the primary partition key on all tables.
                                                                                                                              
                                                                                                                              Key tables: tenants, users, customers, sites, jobs, job_reports, assets, asset_loans, custom_fields, time_entries
                                                                                                                              
                                                                                                                              ## Development Roadmap
                                                                                                                              
                                                                                                                              ### Phase 1 (MVP - Weeks 1-8)
                                                                                                                              - Core user and access control
                                                                                                                              - - Customer and site management
                                                                                                                                - - Job and project creation
                                                                                                                                  - - Time tracking with approvals
                                                                                                                                    - - Equipment and loans
                                                                                                                                      - - Custom fields configuration
                                                                                                                                        - - Basic reporting
                                                                                                                                         
                                                                                                                                          - ### Phase 2 (Post-MVP)
                                                                                                                                          - - Mobile app
                                                                                                                                            - - Advanced reporting
                                                                                                                                              - - External integrations
                                                                                                                                                - - Payroll system
                                                                                                                                                  - - Accounting integration
                                                                                                                                                   
                                                                                                                                                    - ### Phase 3 (Future)
                                                                                                                                                    - - Field team mobile apps
                                                                                                                                                      - - Real-time collaboration
                                                                                                                                                        - - AI-powered scheduling
                                                                                                                                                         
                                                                                                                                                          - ## Testing
                                                                                                                                                         
                                                                                                                                                          - ```bash
                                                                                                                                                            npm run test                  # Unit tests
                                                                                                                                                            npm run test:integration     # Integration tests
                                                                                                                                                            npm run test:coverage        # With coverage
                                                                                                                                                            ```
                                                                                                                                                            
                                                                                                                                                            ## Contributing
                                                                                                                                                            
                                                                                                                                                            1. Fork the repository
                                                                                                                                                            2. 2. Create your feature branch
                                                                                                                                                               3. 3. Commit your changes
                                                                                                                                                                  4. 4. Push to the branch
                                                                                                                                                                     5. 5. Open a Pull Request
                                                                                                                                                                       
                                                                                                                                                                        6. ## Code Standards
                                                                                                                                                                       
                                                                                                                                                                        7. - **ESLint** for code quality
                                                                                                                                                                           - - **Prettier** for formatting
                                                                                                                                                                             - - **TypeScript** for type safety
                                                                                                                                                                               - - **Conventional Commits** for messages
                                                                                                                                                                                
                                                                                                                                                                                 - ## Security
                                                                                                                                                                                
                                                                                                                                                                                 - - JWT token-based authentication with tenant isolation
                                                                                                                                                                                   - - Role-based access control (RBAC) on all endpoints
                                                                                                                                                                                     - - SQL injection prevention through ORM
                                                                                                                                                                                       - - CSRF protection on form submissions
                                                                                                                                                                                         - - Rate limiting on API endpoints
                                                                                                                                                                                           - - HTTPS enforced in production
                                                                                                                                                                                             - - Environment-based secrets management
                                                                                                                                                                                              
                                                                                                                                                                                               - ## Support
                                                                                                                                                                                              
                                                                                                                                                                                               - For issues, questions, or suggestions:
                                                                                                                                                                                               - 1. Check existing [Issues](../../issues)
                                                                                                                                                                                                 2. 2. Review [Documentation](./docs)
                                                                                                                                                                                                    3. 3. Create a new issue with detailed description
                                                                                                                                                                                                      
                                                                                                                                                                                                       4. ## License
                                                                                                                                                                                                      
                                                                                                                                                                                                       5. This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.
                                                                                                                                                                                                      
                                                                                                                                                                                                       6. ---
                                                                                                                                                                                                      
                                                                                                                                                                                                       7. **SMB Platform** — Configurable. Multi-tenant. Ready to scale.
