# projekt
-- Rostou v průběhu let mzdy ve všech odvětvích, nebo v některých klesají?
SELECT industry_branch_code , payroll_year, AVG(value)
FROM t_Lucie_Hladikova_project_SQL_primary_final 
GROUP BY industry_branch_code, payroll_year
