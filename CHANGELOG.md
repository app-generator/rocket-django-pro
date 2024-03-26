# Change Log

## [1.0.1] 2024-02-06
### Changes

- Update [License Terms](https://github.com/app-generator/rocket-django-pro/blob/main/LICENSE.md)

## [1.0.0] 2024-02-06
### Changes

- Codebase Refactoring
  - Celery
  - File Manager
- Minor UI Fixes  

## [0.0.3] 2024-01-31
### Changes

- Deprecate `distutils`
  - use `str2bool`
- Update Deps 
  - `requirements.txt` 

## [0.0.2] 2023-12-13
### Changes

- Added File Manager
- Curate Profile Page
- Update Sidebar

## [0.0.1] 2023-12-02
### Changes

- Generate Sales Model
- Generate API Node for Sales
- Refactor [Charts Page](https://rocket-django.onrender.com/charts/)
- Fix #18 - [Document the API](https://rocket-django.onrender.com/api/docs/)
  - Via `DRF-spectacular`
- Fix #14 - Charts, Render Options  
- Update for MySql/PgSQL Usage
- Update DOCS (readme)
- Fallback to **Django** `4.1.12`
  - To avoid [MySql 8 Dependency](https://stackoverflow.com/questions/75986754/django-db-utils-notsupportederror-mysql-8-or-later-is-required-found-5-7-33)
- Profile Page Updates
  - Added User IMG
  - Change Password 
- ADMIN (Superusers)
  - Edt Users 
- Products (DataTables)
  - Added Edit/Delete/Create controls   
