---
title: Получение информации об удачности загрузки ОbjectListView
sidebar: flexberry-winforms_sidebar
keywords: Windows UI (Контролы)
summary: Объясняется как в обработчике события `ОbjectListView.AfterFillData` получить информацию об успешности загрузки
toc: true
permalink: en/fw_after-fill-data-event-args.html
folder: products/flexberry-winforms/
lang: en
---

В обработчике события `ОbjectListView.AfterFillData` существует возможность получить информацию об успешности загрузки. В качестве параметра события вместо типа `EventArgs` передается его наследник `AfterFillDataEventArgs`.
Тип `AfterFillDataEventArgs` имеет три свойства:

```csharp
        /// <summary>
        /// Исключение, произошедшее во время загрузки
        /// </summary>
        public Exception Exception { get; private set;}
        /// <summary>
        /// Загрузка отменена пользователем
        /// </summary>
        public bool CanceledByUser { get; private set; }
        /// <summary>
        /// Загрузка успешно завершена
        /// </summary>
        public bool IsFillSuccessfullyCompleted { get; private set; }
```

Пример:

```csharp
        private void objectListView1_AfterFillData(object sender, EventArgs e)
        {
            if (e is AfterFillDataEventArgs)
            {
                var afterFillDataEventArgs = e as AfterFillDataEventArgs;
                MessageBox.Show(
                    string.Format("CancelByUser: {0}, Exception: {1}, IsFillSuccessfullyCompleted: {2} ",
                    afterFillDataEventArgs.CanceledByUser, afterFillDataEventArgs.Exception, afterFillDataEventArgs.IsFillSuccessfullyCompleted));
            }
        }
```