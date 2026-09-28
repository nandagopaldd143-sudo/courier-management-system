# Courier Management System (CMS)

Salesforce-based Courier Management System prepared from the provided CMS skill-paper specification.

## Included
- Customer__c
- Shipment__c
- Delivery_Agent__c
- Branch__c
- Delivery_Update__c
- Invoice__c
- Lookup and Master-Detail relationships
- Validation rules
- Record-triggered Flow to update Shipment status from Delivery Update

## Deploy
```bash
sf org login web --alias CMSORG
sf project deploy start --source-dir force-app --target-org CMSORG
```

Or deploy with Salesforce CLI using the manifest:
```bash
sf project deploy start --manifest manifest/package.xml --target-org CMSORG
```

## Main automation
Creating a `Delivery_Update__c` record copies `Status__c` to its related `Shipment__c` record.
