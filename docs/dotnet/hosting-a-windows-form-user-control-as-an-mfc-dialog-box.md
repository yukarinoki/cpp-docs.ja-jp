---
title: ユーザー コントロールを MFC ダイアログ ボックスとしてフォーム、Windows をホストしている |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b356bff4974b43445524d9bc07e1e37c62a6f8d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト
MFC には、このテンプレート クラスは[CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) Windows フォーム ユーザー コントロールをホストできるように (<xref:System.Windows.Forms.UserControl>) モーダルまたはモードレスの MFC ダイアログ ボックスでします。 `CWinFormsDialog` MFC クラスから派生した[CDialog](../mfc/reference/cdialog-class.md)ので、ダイアログ ボックスをモーダルまたはモードレスとして起動することができます。  
  
 プロセスを`CWinFormsDialog`ユーザー コントロールをホストするために使用に似ていますで説明されている[MFC ダイアログ ボックスで Windows フォーム ユーザー コントロールをホストしている](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)です。 ただし、`CWinFormsDialog` は、ユーザー コントロールの初期化およびホストを管理するため、手動でプログラムを作成する必要はありません。  
  
 MFC で使用される Windows フォームを表示するサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)です。  
  
### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには  
  
1.  MFC アプリケーション プロジェクトを作成します。  
  
     **ファイル**メニューの **新規**、クリックして**プロジェクト**です。 **Visual C**フォルダーを選択**MFC アプリケーション**です。  
  
     **名前**ボックスに、入力`MFC03`ソリューションの設定を変更および**ソリューションに追加**です。をクリックして**OK**です。  
  
     **MFC アプリケーション ウィザード**すべての既定値をそのまま使用し、クリックして**完了**です。 これにより、マルチ ドキュメント インターフェイスを持つ MFC アプリケーションが作成されます。  
  
2.  プロジェクトを構成します。  
  
     **ソリューション エクスプ ローラー**を右クリックし、 **MFC03**プロジェクト ノード、および選択**プロパティ**です。 **プロパティ ページ** ダイアログ ボックスが表示されます。  
  
     **プロパティ ページ** ダイアログ ボックスで、**構成プロパティ**ツリー コントロールで、**全般**、次に、**プロジェクトの既定値**セクションで、設定**共通言語ランタイム サポート**に**共通言語ランタイム サポート (/clr)** です。 **[OK]** をクリックします。  
  
3.  .NET コントロールへの参照を追加します。  
  
     **ソリューション エクスプ ローラー**を右クリックし、 **MFC03**プロジェクト ノードと選択**追加**、**参照**です。 **プロパティ ページ**、 をクリックして**新しい参照の追加**、WindowsControlLibrary1 を選択 (下にある、**プロジェクト** タブ)、 をクリック**OK**です。 形式での参照を追加、 [/FU](../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプションは、プログラムのコンパイル。 WindowsControlLibrary1.dll にもコピー、`MFC03`プログラムを実行できるように、プロジェクト ディレクトリ。  
  
4.  stdafx.h の既存の `#include <afxwinforms.h>` ステートメントの最後に `#include` を追加します。  
  
5.  `CDialog` をサブクラスとして持つ新しいクラスを追加します。  
  
     プロジェクト名を右クリックし、`CDialog` をサブクラスとして持つ (CHostForWinForm という名前の) MFC クラスを追加します。 ダイアログ ボックスのリソースは不要なので、リソース ID を削除できます。この操作を行うには、[リソース ビュー] を選択し、[ダイアログ] フォルダーを展開して、IDD_HOSTFORWINFORM リソースを削除します。  次に、コード内のこの ID への参照を削除します。  
  
6.  CHostForWinForm.h ファイルと CHostForWinForm.cpp ファイル内にある `CDialog` を `CWinFormsDialog<WindowsControlLibrary1::UserControl1>` に置き換えます。  
  
7.  CHostForWinForm クラスで DoModal を呼び出します。  
  
     MFC03.cpp で、`#include "HostForWinForm.h"` を追加します。  
  
     CMFC03App::InitInstance の定義内の return ステートメントの前に、次のコードを追加します。  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  プロジェクトをビルドして実行します。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
     次に、MFC アプリケーションから Windows フォーム上のコントロールの状態を監視するコードを追加します。  
  
9. OnInitDialog のハンドラーを追加します。  
  
     表示、**プロパティ**ウィンドウ (F4)。 **クラス ビュー**CHostForWinForm を選択します。 **プロパティ**ウィンドウで、選択をオーバーライドおよび OnInitDialog の行、左側の列内をクリックし、選択\<追加 >。 これにより、次の行が CHostForWinForm.h に追加されます。  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. CHostForWinForm.cpp で、OnInitDialog を次のように定義します。  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. 次に、OnButton1 ハンドラーを追加します。 CHostForWinForm.h 内の CHostForWinForm クラスのパブリック セクションに次の行を追加します。  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     CHostForWinForm.cpp で、次の定義を追加します。  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. プロジェクトをビルドして実行します。 Windows フォーム上のボタンをクリックすると、MFC アプリケーション内のコードが実行されます。  
  
     次に、MFC コードから Windows フォーム上のテキスト ボックスの値を表示するコードを追加します。  
  
13. CHostForWinForm.h 内の CHostForWinForm クラスのパブリック セクションに、次の宣言を追加します。  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. CHostForWinForm.cpp 内の DoDataExchange の定義で、関数の最後に次の 3 行を追加します。  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. CHostForWinForm.cpp 内の OnButton1 の定義で、関数の最後に次の 3 行を追加します。  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. プロジェクトをビルドして実行します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)