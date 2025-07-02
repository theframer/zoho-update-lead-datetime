# 🕒 Zoho Deluge Script: Update Lead with AEST DateTime

This script updates a Zoho CRM **Lead** record by fetching the current datetime in **Australia/Sydney (AEST/AEDT)** timezone from an external API and storing it in a custom field.

---

## 🔍 What does it do?
- Calls `timeapi.io` to get the current time in `Australia/Sydney`.
- Removes microseconds to match ISO format expected by Zoho.
- Adds `+11:00` or `+10:00` offset based on Daylight Saving.
- Updates the `Scheduler_Date_Time` custom field on the Lead record.

---

## 🚀 How to use
- Place this script in a Zoho CRM workflow function or custom button.
- Ensure:
  - `Scheduler_Date_Time` is a Date-Time field in your Leads module.
  - Connection `solution` is configured to call Zoho CRM APIs.
- The script automatically adjusts for DST.

---

## ⚙ Example payload
The script updates your Lead like:
```json
{
  "data": [
    {
      "Scheduler_Date_Time": "2025-07-02T10:40:44+10:00"
    }
  ]
}
