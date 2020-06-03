---
title: MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: 7fc2aad1e0a550fb8f22b311518ae9fb16c076a5
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "79544797"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト

MFC には、モーダルまたはモードレスの MFC ダイアログボックスで Windows フォームユーザーコントロール (<xref:System.Windows.Forms.UserControl>) をホストできるように、テンプレートクラス[CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md)が用意されています。 `CWinFormsDialog` は MFC クラス[CDialog](../mfc/reference/cdialog-class.md)から派生しているため、ダイアログボックスはモーダルまたはモードレスとして起動できます。

`CWinFormsDialog` がユーザーコントロールをホストするために使用するプロセスは、「 [MFC ダイアログボックスでの Windows フォームユーザーコントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)」で説明されている手順と似ています。 ただし、`CWinFormsDialog` は、ユーザー コントロールの初期化およびホストを管理するため、手動でプログラムを作成する必要はありません。

MFC で使用 Windows フォームを示すサンプルアプリケーションについては、「 [mfc と Windows フォームの統合](https://www.microsoft.com/download/details.aspx?id=2113)」を参照してください。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. MFC アプリケーション プロジェクトを作成します。

   **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。 **C++ビジュアル**フォルダーで、 **[MFC アプリケーション]** を選択します。

   **[名前]** ボックスに「`MFC03`」と入力し、ソリューションの設定を **[ソリューションに追加]** に変更します。[ **OK]** をクリックします。

   **MFC アプリケーションウィザード**で、すべての既定値をそのまま使用し、 **[完了]** をクリックします。 これにより、マルチ ドキュメント インターフェイスを持つ MFC アプリケーションが作成されます。

1. プロジェクトを構成します。

   **ソリューションエクスプローラー**で、 **MFC03**プロジェクトノードを右クリックし、 **[プロパティ]** を選択します。 **[プロパティページ]** ダイアログボックスが表示されます。

   **[プロパティページ]** ダイアログボックスの **[構成プロパティ]** ツリーコントロールで、 **[全般]** を選択し、 **[プロジェクトの既定値]** セクションで **[共通言語ランタイムサポート]** を **[共通言語ランタイムサポート (/clr)]** に設定します。 **[OK]** をクリックすると、

1. .NET コントロールへの参照を追加します。

   **ソリューションエクスプローラー**で、 **MFC03**プロジェクトノードを右クリックし、 **[追加]** 、 **[参照]** の順に選択します。 **プロパティ ページ**で、 **新しい参照の追加** をクリックし、**プロジェクト** タブの下の WindowsControlLibrary1 を選択して、 **OK**をクリックします。 これにより、プログラムがコンパイルされるように、 [/fu](../build/reference/fu-name-forced-hash-using-file.md)コンパイラオプションの形式で参照が追加されます。また、WindowsControlLibrary1 を `MFC03` プロジェクトディレクトリにコピーして、プログラムが実行されるようにします。

1. 既存の `#include` ステートメントの最後にある *.pch* (Visual Studio 2017 以前の*stdafx.h* ) に `#include <afxwinforms.h>` を追加します。

1. `CDialog` をサブクラスとして持つ新しいクラスを追加します。

   プロジェクト名を右クリックし、`CDialog` をサブクラスとして持つ (CHostForWinForm という名前の) MFC クラスを追加します。 ダイアログボックスリソースは必要ないため、リソース ID を削除することもできます (**リソースビュー**を選択し、**ダイアログ**フォルダーを展開して `IDD_HOSTFORWINFORM` リソースを削除します)。  次に、コード内のこの ID への参照を削除します。

1. CHostForWinForm.h ファイルと CHostForWinForm.cpp ファイル内にある `CDialog` を `CWinFormsDialog<WindowsControlLibrary1::UserControl1>` に置き換えます。

1. CHostForWinForm クラスで DoModal を呼び出します。

   MFC03.cpp で、`#include "HostForWinForm.h"` を追加します。

   CMFC03App::InitInstance の定義内の return ステートメントの前に、次のコードを追加します。

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. プロジェクトをビルドおよび実行します。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   **[デバッグ]** メニューの **[デバッグなしで開始]** をクリックします。

   次に、MFC アプリケーションから Windows フォーム上のコントロールの状態を監視するコードを追加します。

1. OnInitDialog のハンドラーを追加します。

   **[プロパティ]** ウィンドウ (F4) を表示します。 **クラスビュー**で、[選択] を選択します。 **プロパティ** ウィンドウで、上書き を選択し、OnInitDialog の行で左側の列をクリックし、> の追加 \< 選択します。 これにより、次の行が CHostForWinForm.h に追加されます。

    ```cpp
    virtual BOOL OnInitDialog();
    ```

1. CHostForWinForm.cpp で、OnInitDialog を次のように定義します。

    ```cpp
    BOOL CHostForWinForm::OnInitDialog() {
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);
       return TRUE;
    }
    ```

1. 次に、OnButton1 ハンドラーを追加します。 CHostForWinForm.h 内の CHostForWinForm クラスのパブリック セクションに次の行を追加します。

    ```cpp
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );

    BEGIN_DELEGATE_MAP( CHostForWinForm )
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );
    END_DELEGATE_MAP()
    ```

   CHostForWinForm.cpp で、次の定義を追加します。

    ```cpp
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )
    {
       System::Windows::Forms::MessageBox::Show("test");
    }
    ```

1. プロジェクトをビルドおよび実行します。 Windows フォーム上のボタンをクリックすると、MFC アプリケーション内のコードが実行されます。

    次に、MFC コードから Windows フォーム上のテキスト ボックスの値を表示するコードを追加します。

1. CHostForWinForm.h 内の CHostForWinForm クラスのパブリック セクションに、次の宣言を追加します。

    ```cpp
    CString m_sEditBoxOnWinForm;
    ```

1. CHostForWinForm.cpp 内の DoDataExchange の定義で、関数の最後に次の 3 行を追加します。

    ```cpp
    if (pDX->m_bSaveAndValidate)
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);
    else
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);
    ```

1. CHostForWinForm.cpp 内の OnButton1 の定義で、関数の最後に次の 3 行を追加します。

    ```cpp
    this->UpdateData(TRUE);
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);
    System::Windows::Forms::MessageBox::Show(z);
    ```

1. プロジェクトをビルドおよび実行します。

## <a name="see-also"></a>参照

[MFC で Windows フォームユーザーコントロールを使用して 
を](../dotnet/using-a-windows-form-user-control-in-mfc.md)<xref:System.Windows.Forms.UserControl?displayProperty=fullName>する
