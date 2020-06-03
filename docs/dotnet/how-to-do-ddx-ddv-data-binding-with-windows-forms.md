---
title: '方法: Windows フォームで DDX-DDV データ バインディングを実行する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 31629a4db2559112ba49f5c069b08de7abdfc2db
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754351"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>方法: Windows フォームで DDX/DDV データ バインドを実行する

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)呼び出し[CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol)リソース コントロール ID に一致するコントロールを作成します。 コントロール (`DDX_ManagedControl`ウィザードによって生成されたコード) に使用する場合は、同`CreateManagedControl`じコントロールに対して明示的に呼び出す必要はありません。 `CWinFormsControl`

`DDX_ManagedControl` [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)を呼び出して、リソース ID からコントロールを作成します。 データ交換の場合、Windows フォーム コントロールで DDX/DDV 関数を使用する必要はありません。 代わりに、次の例のように、ダイアログ (またはビュー) クラス`DoDataExchange`のメソッドでマネージ コントロールのプロパティにアクセスするコードを配置できます。

ネイティブ C++ 文字列を .NET ユーザー コントロールにバインドする方法を次の例に示します。

## <a name="example"></a>例

次に示す例は、.NET ユーザー コントロールのユーザー定義`m_str``NameText`プロパティを使用した MFC 文字列の DDX/DDV データ バインディングの例です。

コントロールは[、CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)が初`CMyDlg::DoDataExchange`めて呼び出されたときに作成されるため、参照`m_UserControl`するコードは呼び`DDX_ManagedControl`出しの後に指定する必要があります。

このコードは、「方法 : ダイアログ ボックスでユーザー[コントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)」で作成した MFC01 アプリケーションに実装できます。

CMFC01Dlg の宣言に次のコードを記述します。

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>例

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

## <a name="example"></a>例

次に、[OK] ボタンをクリックするためのハンドラメソッドを追加します。 [**リソース ビュー** ] タブをクリックします。リソース ビューで、`IDD_MFC01_DIALOG`をダブルクリックします。 リソース エディターにダイアログ リソースが表示されます。 次に、[OK]ボタンをダブルクリックします。

ハンドラを次のように定義します。

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>例

そして、BOOL CMFC01Dlg::OnInitDialog() の実装に次の行を追加します。

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

アプリケーションをビルドして実行できる状態になりました。 アプリケーションを閉じると、テキスト ボックス内のテキストがポップアップ メッセージ ボックスに表示されます。

## <a name="see-also"></a>関連項目

[CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
