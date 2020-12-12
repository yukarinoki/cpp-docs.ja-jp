---
description: 詳細については、「ユーザー定義ツール」を参照してください。
title: ユーザー定義のツール
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 4cccd0a68751a2f196c8c2e652088e8939e3f162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263635"
---
# <a name="user-defined-tools"></a>ユーザー定義のツール

MFC では、ユーザー定義ツールがサポートされています。 ユーザー定義ツールは、ユーザーが指定した外部のプログラムを実行する特殊なコマンドです。 カスタマイズプロセスを使用して、ユーザー定義ツールを管理できます。 ただし、アプリケーションオブジェクトが [CWinAppEx クラス](../mfc/reference/cwinappex-class.md)から派生していない場合、このプロセスを使用することはできません。 カスタマイズの詳細については、「 [MFC のカスタマイズ](../mfc/customization-for-mfc.md)」を参照してください。

ユーザー定義ツールのサポートを有効にした場合、[カスタマイズ] ダイアログボックスには自動的に [ **ツール** ] タブが表示されます。次の図は、[ **ツール** ] ページを示しています。

![カスタム ダイアログ ボックスの [ツール] タブ](../mfc/media/custdialogboxtoolstab.png "カスタム ダイアログ ボックスの [ツール] タブ") <br/>
カスタマイズダイアログボックスの [ツール] タブ

## <a name="enabling-user-defined-tools-support"></a>ユーザー定義ツールのサポートの有効化

アプリケーションでユーザー定義ツールを有効にするには、 [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)を呼び出します。 ただし、まず、アプリケーションのリソースファイルで、この呼び出しのパラメーターとして使用するいくつかの定数を定義する必要があります。

リソースエディターで、適切なコマンド ID を使用するダミーコマンドを作成します。 次の例では、 `ID_TOOLS_ENTRY` コマンド ID としてを使用します。 このコマンド ID は、フレームワークによってユーザー定義ツールが挿入される1つまたは複数のメニュー内の場所をマークします。

ユーザー定義ツールを表すには、文字列テーブル内の連続する Id をいくつか確保する必要があります。 設定する文字列の数は、ユーザーが定義できるユーザーツールの最大数と同じです。 次の例では、によって名前が付けられ `ID_USER_TOOL1` てい `ID_USER_TOOL10` ます。

ツールとして呼び出される外部プログラムのディレクトリと引数を選択する際に役立つ提案をユーザーに提供することができます。 これを行うには、リソースエディターで2つのポップアップメニューを作成します。 次の例では、これらにとという名前が付けられ `IDR_MENU_ARGS` てい `IDR_MENU_DIRS` ます。 これらのメニューの各コマンドについて、アプリケーション文字列テーブルに文字列を定義します。 文字列のリソース ID は、コマンド ID と同じである必要があります。

[Cusertool クラス](../mfc/reference/cusertool-class.md)から派生クラスを作成して、既定の実装を置き換えることもできます。 これを行うには、派生クラスのランタイム情報を RUNTIME_CLASS ([Cusertool クラス](../mfc/reference/cusertool-class.md)) ではなく、CWinAppEx:: EnableUserTools の4番目のパラメーターとして渡します。

適切な定数を定義したら、 [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) を呼び出してユーザー定義ツールを有効にします。

次のメソッド呼び出しは、これらの定数を使用する方法を示しています。

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

この例では、[ツール] タブが [ **カスタマイズ** ] ダイアログボックスに表示されます。 フレームワークは、任意のメニューのコマンド ID に一致するすべてのコマンドを、 `ID_TOOLS_ENTRY` ユーザーがメニューを開いたときに、現在定義されているユーザーツールのセットと置き換えます。 コマンド Id は `ID_USER_TOOL1` 、 `ID_USER_TOOL10` ユーザー定義ツール用に予約されています。 クラス [Cusertool クラス](../mfc/reference/cusertool-class.md) は、ユーザーツールの呼び出しを処理します。 [ **カスタマイズ** ] ダイアログボックスの [ツール] タブでは、[引数] フィールドと [ディレクトリの入力] フィールドの右側にあるボタンを使用して、 **IDR_MENU_ARGS** および **IDR_MENU_DIRS** のメニューにアクセスできます。ユーザーがこれらのメニューのいずれかからコマンドを選択すると、フレームワークは、コマンド ID と同じリソース ID を持つ文字列を適切なテキストボックスに追加します。

### <a name="including-predefined-tools"></a>定義済みツールを含む

アプリケーションの起動時に一部のツールを事前に定義する場合は、アプリケーションのメインウィンドウの [CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) メソッドをオーバーライドする必要があります。 その方法では、次の手順を実行する必要があります。

##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame に新しいツールを追加するには

1. [CWinAppEx:: getuserツールマネージャー](../mfc/reference/cwinappex-class.md#getusertoolsmanager)を呼び出して、 [Cuserツールマネージャークラス](../mfc/reference/cusertoolsmanager-class.md)オブジェクトへのポインターを取得します。

1. 作成するすべてのツールに対して、 [Cusertools manager:: CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)を呼び出します。 このメソッドは、 [Cusertool クラス](../mfc/reference/cusertool-class.md) オブジェクトへのポインターを返し、新しく作成されたユーザーツールをツールの内部コレクションに追加します。 [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)の4番目のパラメーターとして[Cusertool クラス](../mfc/reference/cusertool-class.md)の派生クラスのランタイム情報を指定した場合、 [Cusertool manager:: CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)はそのクラスのインスタンスをインスタンス化して返します。

1. 各ツールについて、を設定してテキストラベルを設定し、を `CUserTool::m_strLabel` 呼び出してそのコマンドを設定し `CUserTool::SetCommand` ます。 [Cusertool クラス](../mfc/reference/cusertool-class.md)の既定の実装は、の呼び出しで指定されているプログラムから使用可能なアイコンを自動的に取得し `SetCommand` ます。

## <a name="see-also"></a>関連項目

[MFC のカスタマイズ](../mfc/customization-for-mfc.md)<br/>
[CUserTool クラス](../mfc/reference/cusertool-class.md)<br/>
[Cuserツールマネージャークラス](../mfc/reference/cusertoolsmanager-class.md)<br/>
[CWinAppEx クラス](../mfc/reference/cwinappex-class.md)
