---
description: '詳細については、「方法: Windows フォームで DDX/DDV データバインディングを実行する」を参照してください。'
title: '方法: Windows フォームで DDX-DDV データ バインディングを実行する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 55dfdaac595b6de0369d7db555c40b8cd38d6c01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175652"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>方法: Windows フォームで DDX/DDV データ バインドを実行する

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) は、 [CWinFormsControl:: CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) を呼び出して、リソースコントロール ID に一致するコントロールを作成します。 を `DDX_ManagedControl` `CWinFormsControl` (ウィザードで生成されたコードで) コントロールに対して使用する場合は、 `CreateManagedControl` 同じコントロールに対してを明示的に呼び出すことはできません。

`DDX_ManagedControl` [CWnd::D odataexchange](../mfc/reference/cwnd-class.md#dodataexchange)でを呼び出して、リソース id からコントロールを作成します。 データ交換では、Windows フォームコントロールで DDX/DDV 関数を使用する必要はありません。 代わりに、 `DoDataExchange` 次の例に示すように、ダイアログ (またはビュー) クラスのメソッドでマネージコントロールのプロパティにアクセスするコードを配置できます。

次の例は、ネイティブ C++ 文字列を .NET ユーザーコントロールにバインドする方法を示しています。

## <a name="example-ddxddv-data-binding"></a>例: DDX/DDV データバインディング

次に、 `m_str` .net ユーザーコントロールのユーザー定義プロパティを使用した MFC 文字列の DDX/DDV データバインドの例を示し `NameText` ます。

このコントロールは、 [CDialog:: OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) が初めてを呼び出したときに作成され `CMyDlg::DoDataExchange` ます。そのため、を参照するコードは、 `m_UserControl` 呼び出しの後に指定する必要があり `DDX_ManagedControl` ます。

このコードは、 [「方法: ダイアログボックスにユーザーコントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)する」で作成した mfc01] アプリケーションで実装できます。

CMFC01Dlg の宣言に次のコードを追加します。

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example-implement-dodataexchange"></a>例: DoDataExchange () を実装する

CMFC01Dlg の実装に次のコードを記述します。

```cpp
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
{
   CDialog::DoDataExchange(pDX);
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);

   if (pDX->m_bSaveAndValidate) {
      m_str = m_MyControl->textBox1->Text;
   } else
   {
      m_MyControl->textBox1->Text = gcnew System::String(m_str);
   }
}
```

## <a name="example-add-handler-method"></a>例: ハンドラーメソッドの追加

次に、[OK] ボタンをクリックするためのハンドラーメソッドを追加します。 [ **リソースビュー** ] タブをクリックします。リソースビューで、[] をダブルクリックし `IDD_MFC01_DIALOG` ます。 リソース エディターにダイアログ リソースが表示されます。 次に、[OK] ボタンをダブルクリックします。

次のようにハンドラーを定義します。

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example-set-the-textbox-text"></a>例: テキストボックスのテキストを設定する

次の行を、BOOL CMFC01Dlg:: OnInitDialog () の実装に追加します。

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

アプリケーションをビルドして実行できる状態になりました。 アプリケーションを閉じると、テキストボックス内のテキストがポップアップメッセージボックスに表示されます。

## <a name="see-also"></a>関連項目

[CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
