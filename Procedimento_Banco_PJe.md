# __PROCEDIMENTO DE START/STOP DO BANCO POSTGRES DO PJE__

---

* VMs: 
  - BDU110 – Pje 1i (ativo) BDU111(passivo) BDU112 – pgboucer e pgboucer_7432
  - BDU113 (ativo) – Pje 2i / BDU114(passivo) BDU115
  - BDU116 – Logs PJe Produção

* PARAR O BANCO Postgres:

    - LOGAR COMO ROOT
    - service pgbouncer stop / service pgboucer_7432 stop
    - su - postgres
    - pg_ctl stop -mf

* SUBIR O BANCO Postgres:

    - VOLTAR PARA ROOT
    - DEPOIS QUE VOLTAR
    - su - postgres
    - pg_ctl start

* VOLTAR PARA ROOT
    - service pgbouncer stop / service pgboucer_7432 start
