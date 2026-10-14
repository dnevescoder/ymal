task:
  work_item: 123456

scope:
  project: Customer.Api
  type: api

files:
  modify:
    - Application/Services/CustomerService.cs
    - Api/Controllers/CustomerController.cs

  create:
    - Application/Models/CustomerResponse.cs

dependencies:
  internal:
    - CustomerRepository

  external:
    - CustomerGateway

database_changes: false

breaking_change: false

tests:
  required:
    - CustomerServiceTests
    - CustomerControllerTests

skills:
  - dotnet/api
  - dotnet/application
  - testing/unit

constraints:
  - do_not_change_contract
  - do_not_create_migration