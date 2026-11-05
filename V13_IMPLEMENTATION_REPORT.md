# V13 Implementation Report

## Summary

Rebuilt the South Hardin Maintenance demo around the approved light iPhone 13 visual direction: authentic SH icon, black brand header, red v13 badge, role and school pills, red wave divider, welcome and demo identity, tinted status metrics, prominent work and purchase actions, compact Quick Actions, and fixed rounded four item navigation. The avatar opens a floating demo account menu. No employee identity or email is represented as a real person; all sample identities are labeled demo.

V12 work order and purchase request flows remain local demo flows. Work orders support creation, status updates, assignment toggle, and archive; purchase requests support creation. More now opens working local data screens for employees, preventive schedules, reports with CSV export, inventory, notifications, district settings, assets, and archived work orders. Employee, schedule, inventory, and asset records support add/edit/delete. Settings edit local school choices; reset restores the sample data.

## Files

- `index.html`: responsive visual shell, approved hierarchy, controls, and branding.
- `app.js`: local demo data, navigation, forms, and CRUD behavior.
- `sw.js`: unchanged service worker.

## Verification

- `node --check app.js` passes.
- Major click paths are implemented with empty states and explicit Back buttons.
- Persistence uses browser local storage under `sh13-*` keys (with V12 job/purchase data migration fallback).

## Scope notes

All interactions are local demo behavior. Demo Sign Out returns to the Teacher demo view; it does not claim to authenticate or revoke a real session. The account menu presents Admin, Custodian, and Teacher as demo roles. Asset QR scanning and external district integrations are not part of this local demo.
