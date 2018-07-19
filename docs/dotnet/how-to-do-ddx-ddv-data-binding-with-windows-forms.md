---
title: '方法: Windows フォームで DDX DDV データ バインディングを行う |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2f6992aa0c7238d2dc89a8084c7b870dae23067a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131661"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>方法: Windows フォームで DDX/DDV データ バインディングを実行する
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)呼び出し[CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol)リソース コントロール ID に一致するコントロールを作成するには 使用する場合`DDX_ManagedControl`の`CWinFormsControl`コントロール (ウィザードで生成されたコードで)、呼び出す必要はありません`CreateManagedControl`同じコントロールを明示的にします。  
  
 呼び出す`DDX_ManagedControl`で[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)リソース Id からコントロールを作成します。 データ交換における、Windows フォーム コントロールで DDX/DDV 関数を使用する必要はありません。 マネージ コントロールのプロパティにアクセスするためのコードを配置する代わりに、`DoDataExchange`次の例のように、ダイアログ (またはビュー) のクラスのメソッドです。  
  
 次の例では、ネイティブ C++ 文字列を .NET ユーザー コントロールにバインドする方法を示します。  
  
## <a name="example"></a>例  
 MFC 文字列の DDX/DDV データ バインディングの例を次に示します`m_str`ユーザー定義`NameText`.NET ユーザー コントロールのプロパティです。  
  
 コントロールが作成された[CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)呼び出し`CMyDlg::DoDataExchange`を初めて、そのため、コードを参照する`m_UserControl`後に続く必要があります、`DDX_ManagedControl`を呼び出します。  
  
 作成した MFC01 アプリケーションでこのコードを実装する[する方法: ダイアログ ボックスで、ユーザー コントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)です。  
  
 CMFC01Dlg の宣言で、次のコードを配置します。  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## <a name="example"></a>例  
 CMFC01Dlg の実装で、次のコードを配置します。  
  
```  
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
 [Ok] ボタンのクリック ハンドラー メソッドを追加します。 クリックして、**リソース ビュー**タブです。リソース ビューでのダブルクリック`IDD_MFC01_DIALOG`です。 ダイアログ リソースでは、リソース エディターで表示されます。 [Ok] ボタンがダブルクリックし.  
  
 ハンドラーを次のように定義します。  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## <a name="example"></a>例  
 BOOL CMFC01Dlg::OnInitDialog() の実装を次の行を追加します。  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 ビルドをアプリケーションを実行できます。 アプリケーションの終了時に、テキスト ボックスに入力されたテキスト、ポップアップ メッセージ ボックスに表示されることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../mfc/reference/cwinformscontrol-class.md)   
 [DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)   
 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)