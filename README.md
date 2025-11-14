# Desktop Refactored
This is an upgrade of the Desktop site from using Ext JS 5.0.1 and a PHP backend to a more modern, swish, LTS, robust and well-known set of frontend and backend frameworks.

## Design Overview ##

[Full Design Overview](https://docs.google.com/document/d/1WpLhAvyYArVExlRfbRHsGEbE9FZy98KjvepDyl9lf9E/edit?usp=sharing)

### Frontend ###
- React JS (latest LTS version)
- Vite - build tool
- Axios - querying backend
- Libraries:
    - MUI (Material UI) - modern UI components, layouts, forms etc.
    - AG Grid - replaces Ext.data.Store for grid viewing and inline row editing
    - React-rnd - replaces Ext.window.Window with resizable, draggable forms
    - Recharts - replaces Ext.chart.Chart
    - Tailwind - CSS styling (these libraries already implement their own styling anyway)

### Backend ###
Since the entire backend is already written in PHP, it makes sense to replace it with a well-known, lightweight PHP framework, instead of re-writing everything in JavaScript.

- Symfony 6.4 (latest LTS version) + PHP 8.4.12 - PHP framework with built-in ORM and MVC pattern
- MySQL - database is altered through ORM migrations (no raw queries anymore)
- Libraries:
    - symfony/mailer - built-in email service replacing PHPMailer
    - PhpSpreadsheet - replaces deprecated PHPExcel (same developers)

## Terminal Setup Instructions ##

1. Clone the repository using SSH
2. `cd` into the `backend` folder
3. Type `composer install` to install all required packages
4. Type `symfony server:start` to start the Symfony backend server
5. Open a new terminal instance whilst keeping the Symfony process alive on the other terminal
6. `cd` into the `frontend` folder
7. Type `npm install` to install all required React packages and dependencies
8. type `npm run dev` to start the React + Vite frontend server



