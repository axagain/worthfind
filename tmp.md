AR202608040004 这个单号对应的是可以的
SELECT
    a.bill_no,
    a.id AS head_id,
    b.id AS line_id,
    b.expense_item,
    t4.code AS expense_type_code,
    t4.name AS expense_type_name,
    b.fee_item_id,
    t5.id AS fee_item_config_id,
    t5.name AS fee_item_name
FROM public.fin_accounts_receivable_bill_head AS a
LEFT JOIN public.fin_accounts_receivable_bill_line AS b
    ON b.head_id = a.id
    AND b.disabled_by = 0
LEFT JOIN public.fin_conf_expense_type AS t4
    ON b.expense_item = t4.code
LEFT JOIN public.fin_way_bill_fee_item_config AS t5
    ON b.fee_item_id = t5.id
WHERE a.disabled_by = 0
  AND a.bill_no = 'AR202608040004'
ORDER BY b.id;
