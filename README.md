# Examen Final - Cloud Computing
**Universidad Francisco de Paula Santander Ocaña**  
**Asignatura:** Cloud Computing  
**Docente:** Wilder Andrés Duarte Neira  

## Integrantes
| Código | Nombre |
|--------|--------|
| 191997 | Verónica Sánchez Beleño |
| 191991 | Mayerly Araque Durán |

## Descripción
Implementación de Infraestructura como Código (IaC) en AWS mediante CloudFormation y GitHub Actions para la empresa CloudComputing Electiva S.A.

## Estructura del proyecto
├── .github/
│   └── workflows/
│       ├── deploy.yml       # Workflow de despliegue
│       └── destroy.yml      # Workflow de destrucción
└── stacks/
    ├── security.yml         # Stack 1 - Security Groups
    ├── ec2.yml              # Stack 2 - EC2 con Elastic IP
    ├── alb-asg.yml          # Stack 3 - ALB, ASG, Launch Template
    └── automation.yml       # Stack 4 - Automatización programada

## Stacks
- **Stack 1 - Security:** Security Groups para EC2 y ALB
- **Stack 2 - EC2:** Instancia EC2 con Apache y Elastic IP
- **Stack 3 - ALB-ASG:** Load Balancer, Auto Scaling Group y Warm Pool
- **Stack 4 - Automation:** Acciones programadas y Launch Template v2

## Workflows
- deploy.yml — Se ejecuta automáticamente al hacer push en main
- destroy.yml — Se ejecuta manualmente desde GitHub Actions

## Orden de despliegue
Security → EC2 → ALB-ASG → Automation

## Orden de destrucción
Automation → ALB-ASG → EC2 → Security
