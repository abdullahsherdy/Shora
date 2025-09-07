# 🏛️ Shora - Comprehensive Legal Platform API

[![.NET](https://img.shields.io/badge/.NET-9.0-blue)](https://dotnet.microsoft.com/)
[![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-9.0-green)](https://docs.microsoft.com/en-us/aspnet/core/)
[![Entity Framework](https://img.shields.io/badge/Entity%20Framework-9.0-orange)](https://docs.microsoft.com/en-us/ef/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Overview

**Shora** is a sophisticated legal platform designed to bridge the gap between clients and legal professionals. Built with modern .NET technologies and following Clean Architecture principles, this comprehensive system provides full management of legal cases, user authentication, role-based access control, and professional networking for the legal industry.

### 🎯 Vision
To create a digital ecosystem where legal services are accessible, transparent, and efficiently managed through technology.

## ✨ Key Features

### 🔐 Authentication & Authorization
- **Secure JWT Authentication**: Industry-standard token-based authentication
- **OAuth 2.0 Integration**: 🚧 **Currently in Development** - Third-party authentication providers
- **Multi-Role System**: Client, Lawyer, Law Firm, and Admin roles
- **Password Security**: Advanced password complexity requirements
- **Role-Based Access Control**: Granular permissions for different user types
- **API Endpoint Protection**: Comprehensive security across all endpoints

### 📋 Legal Case Management
- **Full CRUD Operations**: Create, read, update, and delete cases
- **Case Categorization**: Organize cases by type and legal specialty
- **Status Tracking**: Real-time case status monitoring
- **Location-Based Organization**: Cases organized by geographical location
- **File Attachment Support**: Document and evidence management
- **Case Assignment**: Assign cases to lawyers and law firms

### 👥 Advanced User Management
- **Client Portal**: Clients can create, track, and manage their legal cases
- **Lawyer Dashboard**: Lawyers can manage assigned cases and client interactions
- **Law Firm Management**: Comprehensive team and case management for law firms
- **Admin Panel**: Full system administration and user management
- **Profile Management**: Detailed user profiles with professional information

### 💬 Communication System
- **Case Comments**: Threaded discussions on legal cases
- **Comment History**: Complete audit trail of case communications
- **User Interactions**: Professional networking capabilities

### 📊 Subscription & Service Management
- **Subscription Tracking**: Manage service subscriptions and billing
- **Service Plans**: Different tiers of legal services
- **Status Monitoring**: Track subscription status and renewals

## 🏗️ Technical Architecture

### Clean Architecture Implementation

```
┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│  ┌─────────────────┐  ┌─────────────────┐  ┌──────────────┐ │
│  │   Controllers   │  │      DTOs       │  │   Swagger    │ │
│  │                 │  │                 │  │              │ │
│  └─────────────────┘  └─────────────────┘  └──────────────┘ │
├─────────────────────────────────────────────────────────────┤
│                    Application Layer                        │
│  ┌─────────────────┐  ┌─────────────────┐  ┌──────────────┐ │
│  │   Commands &    │  │    Services     │  │ Validations  │ │
│  │    Queries      │  │                 │  │              │ │
│  └─────────────────┘  └─────────────────┘  └──────────────┘ │
├─────────────────────────────────────────────────────────────┤
│                      Domain Layer                           │
│  ┌─────────────────┐  ┌─────────────────┐  ┌──────────────┐ │
│  │    Entities     │  │  Value Objects  │  │    Enums     │ │
│  │                 │  │                 │  │              │ │
│  └─────────────────┘  └─────────────────┘  └──────────────┘ │
├─────────────────────────────────────────────────────────────┤
│                  Infrastructure Layer                       │
│  ┌─────────────────┐  ┌─────────────────┐  ┌──────────────┐ │
│  │   Repository    │  │   DbContext     │  │  Migrations  │ │
│  │                 │  │                 │  │              │ │
│  └─────────────────┘  └─────────────────┘  └──────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

### 🎯 Design Patterns & Principles

#### CQRS (Command Query Responsibility Segregation)
- **Commands**: Handle data modifications (Create, Update, Delete)
- **Queries**: Handle data retrieval (GetAll, GetById, GetWithSpecifications)
- **Handlers**: Process commands and queries with business logic
- **MediatR Integration**: Decoupled request/response handling

#### Generic Repository Pattern
- **Generic Interfaces**: `IGenaricRepostry<T>`, `ICommandRepository<T>`, `IQueryRepository<T>`
- **Automatic Handler Registration**: Dynamic registration for all entities
- **Specification Pattern**: Complex query building with `BaseSpacfication<T>`

#### Domain-Driven Design (DDD)
- **Rich Domain Models**: Business logic encapsulated in entities
- **Value Objects**: Immutable objects representing concepts
- **Aggregate Roots**: Consistency boundaries for related entities

## 🛠️ Technology Stack

### Core Framework
| Technology | Version | Purpose |
|------------|---------|----------|
| **.NET** | 9.0 | Core runtime and framework |
| **ASP.NET Core** | 9.0 | Web API development |
| **C#** | 12.0 | Primary programming language |

### Data & Persistence
| Technology | Version | Purpose |
|------------|---------|----------|
| **Entity Framework Core** | 9.0.8 | Object-Relational Mapping (ORM) |
| **SQL Server** | Latest | Primary database |
| **EF Core Migrations** | 9.0.8 | Database schema versioning |

### Authentication & Security
| Technology | Version | Purpose |
|------------|---------|----------|
| **ASP.NET Core Identity** | 9.0.8 | User management and authentication |
| **JWT Bearer** | 9.0.4 | Token-based authentication |
| **System.IdentityModel.Tokens.Jwt** | 8.3.0 | JWT token handling |
| **OAuth 2.0** | 🚧 In Progress | Third-party authentication providers |

### Architecture & Patterns
| Technology | Version | Purpose |
|------------|---------|----------|
| **MediatR** | 13.0.0 | CQRS and mediator pattern |
| **AutoMapper** | 12.0.1 | Object-to-object mapping |

### API Documentation
| Technology | Version | Purpose |
|------------|---------|----------|
| **Swagger/OpenAPI** | 9.0.3 | API documentation and testing |
| **Microsoft.AspNetCore.OpenApi** | 9.0.4 | OpenAPI specification |

## 📁 Project Structure

```
Shora/
├── 🎯 shora/                          # Presentation Layer (API)
│   ├── Controllers/
│   │   ├── AuthController.cs          # Authentication endpoints
│   │   ├── CasesController.cs         # Case management endpoints
│   │   └── WeatherForecastController.cs
│   ├── Dtos/                          # API-specific DTOs
│   │   └── Cases/
│   │       ├── CaseCreateDto.cs
│   │       ├── CaseListDto.cs
│   │       ├── CaseUpdateDto.cs
│   │       └── GetCaseDto.cs
│   ├── Extensions/
│   │   └── MapperProfile.cs           # AutoMapper configuration
│   ├── Program.cs                     # Application entry point
│   ├── appsettings.json              # Configuration settings
│   └── shora.csproj                  # Project file
│
├── 🧠 ApplicationLayer/               # Application Layer (Use Cases)
│   ├── Features/                      # Feature-based organization
│   │   ├── Auth/                      # Authentication features
│   │   │   ├── Commands/
│   │   │   │   ├── LoginCommand.cs
│   │   │   │   └── RegisterCommand.cs
│   │   │   └── Handlers/
│   │   │       ├── LoginCommandHandler.cs
│   │   │       └── RegisterCommandHandler.cs
│   │   ├── Commend/                   # Generic commands
│   │   │   ├── CreateCommand.cs
│   │   │   ├── CreateCommandHandler.cs
│   │   │   ├── UpdateCommand.cs
│   │   │   ├── UpdateCommandHandler.cs
│   │   │   ├── DeleteCommand.cs
│   │   │   └── DeleteCommandHandler.cs
│   │   ├── Query/                     # Generic queries
│   │   │   ├── GetAllQuery.cs
│   │   │   ├── GetAllQueryHandler.cs
│   │   │   ├── GetByIdQuery.cs
│   │   │   ├── GetByIdQueryHandler.cs
│   │   │   ├── GetAllWithSpecQuery.cs
│   │   │   ├── GetAllWithSpecHandler.cs
│   │   │   ├── GetByIdWithSpecQuery.cs
│   │   │   └── GetByIdWithSpecHandler.cs
│   │   └── Spacification/             # Query specifications
│   │       ├── BaseSpacfication.cs
│   │       └── spacificationEvalator.cs
│   ├── DTOs/                          # Data Transfer Objects
│   │   └── Auth/
│   │       ├── LoginDto.cs
│   │       ├── RegisterDto.cs
│   │       └── AuthResponseDto.cs
│   ├── Services/                      # Application services
│   │   ├── IJwtTokenService.cs
│   │   └── JwtTokenService.cs
│   ├── Configuration/
│   │   └── JwtSettings.cs             # JWT configuration model
│   ├── Extensions/
│   │   └── ServiceCollectionExtensions.cs # DI extensions
│   └── ApplicationLayer.csproj
│
├── 🏛️ DomianLayar/                   # Domain Layer (Business Logic)
│   ├── Entities/                      # Domain entities
│   │   ├── BaseClass.cs              # Base entity class
│   │   ├── BaseUser.cs               # User base class (Identity)
│   │   ├── Case.cs                   # Legal case entity
│   │   ├── comment.cs                # Comment entity
│   │   ├── Post.cs                   # Post entity
│   │   ├── subscripstion.cs          # Subscription entity
│   │   └── Users/                    # User specializations
│   │       ├── client.cs             # Client entity
│   │       ├── Lawyer.cs             # Lawyer entity
│   │       └── LawFirm.cs            # Law firm entity
│   ├── Enums/                        # Domain enumerations
│   │   ├── Case.cs
│   │   ├── CaseStatus.cs
│   │   ├── UserRole.cs
│   │   └── UserRoles.cs
│   ├── ValueObjects/                 # Value objects
│   │   ├── Address.cs
│   │   └── ContactInfo.cs
│   ├── contract/                     # Domain interfaces
│   │   ├── IAggregateRoot.cs
│   │   ├── ICommandRepository.cs
│   │   ├── IGenaricRepostry.cs
│   │   ├── IQueryRepository.cs
│   │   └── Ispacfiaction.cs
│   └── DomianLayar.csproj
│
└── 🔧 InfrastructureLayer/           # Infrastructure Layer (Data & External Services)
    ├── GenaricRepostory/
    │   └── GenaricRepostry.cs        # Generic repository implementation
    ├── Migrations/                   # EF Core migrations
    │   ├── 20250818112639_sas4110.cs
    │   ├── 20250818200355_sisi.cs
    │   ├── 20250905031506_sssad.cs
    │   └── ShoraDbContextModelSnapshot.cs
    ├── ٍShoraDbContext.cs            # Database context
    └── InfrastructureLayer.csproj
```

### 🏗️ Architecture Flow

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Controllers   │ ──▶ │   Commands &    │ ──▶ │    Handlers     │
│  (Presentation) │    │    Queries      │    │ (Application)   │
│                 │    │ (Application)   │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│      DTOs       │    │    Services     │    │   Repository    │
│  (Data Transfer)│    │ (Business Logic)│    │ (Infrastructure)│
│                 │    │                 │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                │                       │
                                ▼                       ▼
                       ┌─────────────────┐    ┌─────────────────┐
                       │    Entities     │    │   Database      │
                       │   (Domain)      │    │  (SQL Server)   │
                       │                 │    │                 │
                       └─────────────────┘    └─────────────────┘
```

### 📊 Layer Dependencies

- **Presentation Layer** → Application Layer
- **Application Layer** → Domain Layer  
- **Infrastructure Layer** → Application Layer + Domain Layer
- **Domain Layer** → No dependencies (Pure business logic)

## 🚀 Installation & Setup

### Prerequisites
- **.NET 9.0 SDK** or later
- **SQL Server** (LocalDB, Express, or Full version)
- **Visual Studio 2022** or **VS Code** with C# extension
- **Git** for version control

### Step-by-Step Installation

#### 1. Clone the Repository
```bash
git clone https://github.com/abdullahsherdy/Shora.git
cd Shora
```

#### 2. Restore NuGet Packages
```bash
dotnet restore
```

#### 3. Configure Database
Update the connection string in `shora/appsettings.json`:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=ShoraDB;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}
```

#### 4. Apply Database Migrations
```bash
cd InfrastructureLayer
dotnet ef database update --startup-project ../shora
```

#### 5. Build the Solution
```bash
dotnet build
```

#### 6. Run the Application
```bash
cd shora
dotnet run
```

#### 7. Access the Application
- **Swagger UI**: https://localhost:7000/swagger
- **API Base URL**: https://localhost:7000/api

## 👥 Contact & Team

### 📞 Contact Information
- **Developers**: AbdullahSherdy & AbdullahHisham
- **GitHub Profiles**: [@abdullahsherdy](https://github.com/abdullahsherdy) [@abdullah20020](https://github.com/abdullah20020)
- **Project Repository**: [Shora Legal Platform](https://github.com/abdullahsherdy/Shora)
- **Email**: Available through GitHub profile

### 🚀 Support & Community
- **Issues**: Report bugs and feature requests via [GitHub Issues](https://github.com/abdullahsherdy/Shora)
- **Discussions**: Join project discussions on [GitHub Discussions](https://github.com/abdullahsherdy/Shora/discussions)
- **Documentation**: Comprehensive docs available in the repository
- **Wiki**: Additional resources and guides in the [project wiki](https://github.com/abdullahsherdy/Shora/wiki)

### 🌟 Contributing
We welcome contributions from the community! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details on:
- Code of Conduct
- Development setup
- Pull request process
- Coding standards

### 💬 Professional Services
For enterprise implementations, custom development, or professional consulting services, please contact through GitHub or create an issue with the "enterprise" label.

## 🕰️ Project Roadmap & Future Development

### 🏁 Current Status: **Active Development**

### 🚧 Currently Working On
- [🔄] **OAuth 2.0 Integration**: Third-party authentication providers (Google, Microsoft, GitHub)
- [🔄] **Enhanced Authentication**: Multiple authentication methods and providers
- [🔄] **Security Improvements**: Advanced authentication workflows

### Phase 1: Core Enhancements 
- [ ] **Notifications System**: Real-time notifications for case updates
- [ ] **File Management**: Enhanced document upload and management  
- [ ] **Advanced Search**: Full-text search capabilities for cases
- [ ] **Audit Trail**: Complete audit logging for all operations

### Phase 2: Advanced Features 
- [ ] **Payment Gateway Integration**: Electronic payment processing
- [ ] **Rating & Review System**: Client feedback and lawyer ratings
- [ ] **Advanced Reporting**: Analytics and reporting dashboard
- [ ] **Mobile API**: Mobile-optimized endpoints

### Phase 3: Enterprise Features 
- [ ] **Background Jobs (Hangfire)**: Scheduled tasks and background processing
- [ ] **Real-time Chat (SignalR)**: Live communication system
- [ ] **Multi-tenancy**: Support for multiple law firm instances

### Phase 4: Scalability & Performance 
- [ ] **Microservices Architecture**: Break down into smaller services
- [ ] **Event Sourcing**: Implement event-driven architecture
- [ ] **Advanced CQRS**: Event Store implementation
- [ ] **Containerization**: Docker and Kubernetes support

## 📊 Project Statistics

- **Lines of Code**: ~3,000+
- **Classes**: 60+
- **API Endpoints**: 15+
- **Database Tables**: 8+
- **Supported Roles**: 4
- **Architecture Layers**: 4
- **Design Patterns**: 5+ (CQRS, Repository, Specification, etc.)

## 📜 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Abdullah

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

## 🙏 Acknowledgments

- **Microsoft** for the excellent .NET ecosystem
- **MediatR** for the CQRS implementation  
- **Entity Framework** team for the robust ORM
- **ASP.NET Core** team for the powerful web framework
- **Open Source Community** for the various packages and tools

---

**Note**: This project is under active development. Some features may contain bugs or need improvements. We welcome contributions and feedback from the community.

---

*Built with ❤️ using .NET 9.0 and Clean Architecture principles*
