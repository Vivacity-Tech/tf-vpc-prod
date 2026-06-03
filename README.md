# tf-vpc-prod (Production)

**PRODUCTION INFRASTRUCTURE** - VPC for production environment only.

## ⚠️ CAUTION

This repository manages production network infrastructure. All changes require:
- Code review (minimum 2 approvals)
- Terraform plan review before apply
- Testing in staging environment first

## Configuration

**Terraform Cloud Workspace**: `vpc-prod`

**Environment Variables** (set in TFC):
- `TF_VAR_gcp_project = vivacity-tech-dream`
- `TF_VAR_gcp_region = us-central1`

## Resources

- Production VPC network
- App subnet (10.0.1.0/24)
- Database subnet (10.0.2.0/24)
- GKE subnet (10.0.3.0/24)

## Outputs

- `vpc_id` - VPC network ID
- `vpc_name` - VPC network name
- `app_subnet_id` - App subnet ID
- `db_subnet_id` - Database subnet ID
- `gke_subnet_id` - GKE subnet ID

## Dependencies

None (foundation module)

## Applying Changes

1. Make changes in feature branch
2. Create pull request
3. Wait for 2+ approvals
4. Merge to main
5. GitHub Actions will run `terraform plan`
6. Review plan output
7. Manual approval required to apply

## Rollback

In case of emergency:
```bash
git revert <commit-sha>
git push origin main
```