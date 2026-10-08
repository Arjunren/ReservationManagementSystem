# Reservation Management System

## Overview

A secure TypeScript API for resource discovery, availability checks, conflict-free reservations, approvals, cancellations, and reservation reporting.

## Features

Admin/Customer roles, resource catalog, availability lookup, capacity enforcement, transactional overlap prevention, server-calculated totals, customer ownership, controlled states, pagination, event history, and dashboard.

## Technology Stack

Node.js 24, TypeScript 7, Express 5, built-in SQLite, Zod 4, Vitest 5, and Docker.

## Requirements / Installation

Install Node.js 24+ and npm 11+, then run `npm install`.

## Environment Variables

Set `PORT`, `DB_PATH`, and `CORS_ORIGIN` according to `.env.example`.

## Database Setup

The migration runs automatically. Development users and sample resources seed only into an empty database.

## Running the Application

Run `npm run dev`, or `npm run build && npm start`.

## Running Tests

Run `npm run check`. Tests cover pricing, overlaps, capacity, ownership, and workflow rules.

## Default Development Accounts

`admin` and `customer`, password `ChangeMe123!` (development only).

## API Endpoints

`POST /api/auth/login`, `GET /api/resources`, `GET /api/availability`, `GET/POST /api/reservations`, `PATCH /api/reservations/:id/status`, and `GET /api/dashboard`.

## Folder Structure

`src/services` owns booking transactions, `src/app.ts` owns routes/validation, `src/auth.ts` owns sessions, `migrations` owns schema, and `tests` owns business tests.

## Security Notes

Scrypt hashes, digested expiring tokens, roles, customer ownership, parameterized SQL, write transactions, capacity/conflict checks, server-side totals, runtime validation, Helmet, CORS, rate limiting, and safe errors are implemented. Use HTTPS and remove demo credentials for production.

## Known Limitations

Payments, recurring reservations, waitlists, external calendars, and time-zone conversion are outside scope.

## License

MIT
