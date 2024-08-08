# projekt
-- Rostou v průběhu let mzdy ve všech odvětvích, nebo v některých klesají?

-- Vytvoření tabulky
CREATE TABLE t_Lucie_Hladikova_project_SQL_primary_final AS
SELECT * 
FROM czechia_payroll cp
JOIN czechia_payroll_industry_branch cpib 
     ON cp.industry_branch_code = cpib.code
WHERE cp.value_type_code = 5958 AND cp.value IS NOT NULL;


-- Zobrazení průměrných mezd za jednotlivé roky řazené dle typu odvětví

SELECT name , payroll_year, ROUND(AVG(value)) AS prumerna_mzda
FROM t_Lucie_Hladikova_project_SQL_primary_final 
WHERE industry_branch_code IS NOT NULL
GROUP BY name, payroll_year
