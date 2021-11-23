# PS-AD-Password_Notify

This is a powerShell script designed to be run on a schedule to automatically email Active Directory users of soon-to-expire and recently-expired passwords.

This version is rewritten of the original v1.4 by Robert Pearman from https://gallery.technet.microsoft.com/Password-Expiry-Email-177c3e27. Pearman's 2.x version was completely re-written.

# Rewritten Things:

    A SearchBase is required.
    OU ExcludeList
    When logging, the CSV will always be overwritten. (unless you specify a variable file name such as "c:\PS-pwd-expiry-$(Get-Date -format yyyyMMdd-HHmmss).csv")
    Accounts with recently-expired passwords can be notified by specifying a "negativedays" value.
    Email attempts will handle basic errors, but nothing more. This script does not account for SMTP credentials.
    Accounts with MaxPasswordAge 00:00:00 (never) are skipped. (Same as PasswordNeverExpires.)
    Testing-mode will allow a specified number of sample notifications to be emailed to the Administrator(s). (Rather than defaulting to all users' expiration emails.)
    Processing information and basic statistics are written to console.
    When logging, the CSV file and basic statistics will be emailed to the specified Administrator(s).
