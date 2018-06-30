---
title: 'TN006: メッセージ マップ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.messages.maps
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c4bc820c6b54e055235c1bd29bd55ccfc032c92
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121677"
---
# <a name="tn006-message-maps"></a>テクニカル ノート 6: メッセージ マップ

ここでは、MFC メッセージ マップ機能について説明します。

## <a name="the-problem"></a>問題を

Microsoft Windows では、そのメッセージング機能を使用するウィンドウ クラスの仮想関数を実装します。 関連するメッセージの数が多いため Windows メッセージごとに個別の仮想関数を提供する、非常に大規模な vtable を作成します。

システム定義の Windows メッセージの数が時間の経過と共に変化し、メッセージがマップするため、アプリケーションは、独自の Windows メッセージを定義することができます、ためをインターフェイスの変更が既存のコードを中断するを妨げる間接参照のレベルを提供します。

## <a name="overview"></a>概要

MFC には、代わりに、ウィンドウに送信されたメッセージを処理する従来の Windows ベースのプログラムで使用された switch ステートメントが用意されています。 ウィンドウによってメッセージが受信されると、適切なメソッドが自動的にできるように、メッセージからメソッドへのマッピングを定義できます。 このメッセージ マップ機能は仮想関数に似ていますが C++ の仮想関数では実現できないその他の利点です。

## <a name="defining-a-message-map"></a>メッセージ マップを定義します。

[DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map)マクロは、クラスの 3 つのメンバーを宣言します。

- AFX_MSGMAP_ENTRY エントリのプライベート配列と呼ばれる *_messageEntries*です。

- プロテクト AFX_MSGMAP 構造体と呼ばれる*messageMap*を指す、 *_messageEntries*配列。

- Protected で呼び出される仮想関数`GetMessageMap`のアドレスを返す*messageMap*です。

メッセージ マップを使用して任意のクラスの宣言では、このマクロを含める必要があります。 慣例により、クラス宣言の最後になります。 例えば:

```cpp
class CMyWnd : public CMyParentWndClass
{
    // my stuff...

protected:
    //{{AFX_MSG(CMyWnd)
    afx_msg void OnPaint();
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};
```

これは、新しいクラスを作成するときに、AppWizard と ClassWizard で生成された形式です。 //{{と//}} ClassWizard の角かっこが必要です。

メッセージ マップのテーブルは、一連のメッセージ マップ エントリに展開されるマクロを使用して定義されます。 テーブルが始まり、 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)マクロの呼び出しは、このメッセージ マップで処理されるクラスと未処理のメッセージが渡され、親クラスを定義します。 テーブル、 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)マクロの呼び出しです。

これらの 2 つのマクロ呼び出しの間、このメッセージ マップで処理するには、各メッセージのエントリです。 各標準の Windows メッセージには、フォーム ON_WM_ のマクロ*MESSAGE_NAME*そのメッセージのエントリを生成します。

標準的な関数のシグネチャが定義されて Windows メッセージごとのパラメーターをアンパックし、タイプ セーフを提供します。 Afxwin.h、宣言内のファイルで見つかる可能性があるこれらの署名の[CWnd](../mfc/reference/cwnd-class.md)です。 それぞれが、キーワードでマークされた**afx_msg**を識別しやすくします。

> [!NOTE]
> ClassWizard では、使用することが必要です、 **afx_msg**メッセージ マップ ハンドラーの宣言でキーワード。

 これらの関数シグネチャは、単純な規則を使用して取得しました。 関数の名前は、常にで始まる`"On`"です。 これは後に、"WM _ で Windows メッセージの名前と大文字で入力の各単語の最初の文字。 パラメーターの順序は*wParam*続く`LOWORD`(*lParam*) し、 `HIWORD`(*lParam*)。 使用されていないパラメーターは渡されません。 MFC クラスによってラップされているすべてのハンドルは、適切な MFC オブジェクトへのポインターに変換されます。 次の例が WM_PAINT メッセージを処理し、発生する方法を示しています、`CMyWnd::OnPaint`に呼び出される関数。

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

 任意の関数またはクラス定義のスコープ外メッセージ マップ テーブルを定義する必要があります。 Extern"C"ブロックに配置する必要があります。

> [!NOTE]
> ClassWizard の間に発生するメッセージ マップ エントリを変更、//{{と//}} コメントの角かっこです。

## <a name="user-defined-windows-messages"></a>ユーザー定義の Windows メッセージ

使用して、ユーザー定義メッセージをメッセージ マップに含めることは、 [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message)マクロです。 このマクロは、メッセージの数とフォームのメソッドを受け取ります。

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

この例では、ユーザー定義メッセージの標準的な WM_USER 基本クラスから派生した Windows メッセージ ID を持つカスタム メッセージのハンドラーを確立します。 次の例では、このハンドラーを呼び出す方法を示します。

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

この方法を使用するユーザー定義のメッセージの範囲は、WM_USER 0x7fff の範囲でなければなりません。

> [!NOTE]
> ClassWizard では、ClassWizard のユーザー インターフェイスからの入力の ON_MESSAGE ハンドラー ルーチンをサポートしていません。 Visual C のエディターから手動で入力する必要があります。 ClassWizard では、これらのエントリが解析され、その他のメッセージ マップ エントリと同様に参照できます。

## <a name="registered-windows-messages"></a>登録済み Windows メッセージ

[を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)関数を使用して、システム全体で一意であることが保証されている新しいウィンドウ メッセージを定義します。 ON_REGISTERED_MESSAGE マクロを使用すると、これらのメッセージを処理します。 このマクロの名前を受け入れる、 *UINT 近く*登録された windows メッセージ ID を含む変数 次に例を示します。

```cpp
class CMyWnd : public CMyParentWndClass
{
public:
    CMyWnd();

    //{{AFX_MSG(CMyWnd)
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};

static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

登録済み Windows メッセージ ID 変数 (この例では WM_FIND) を指定する必要があります、 *NEAR* ON_REGISTERED_MESSAGE の実装方法により、変数です。

この方法を使用するユーザー定義のメッセージの範囲は、0xC000 に 0 xffff の範囲になります。

> [!NOTE]
> ClassWizard では、ClassWizard のユーザー インターフェイスからの入力の ON_REGISTERED_MESSAGE ハンドラー ルーチンをサポートしていません。 テキスト エディターから手動で入力する必要があります。 ClassWizard では、これらのエントリが解析され、その他のメッセージ マップ エントリと同様に参照できます。

## <a name="command-messages"></a>コマンド メッセージ

ON_COMMAND マクロとメッセージ マップで、メニューとアクセラレータからコマンド メッセージが処理されます。 このマクロは、コマンド ID とメソッドを受け取ります。 持つ特定の WM_COMMAND メッセージのみを*wParam* ID は、メッセージ マップ エントリで指定されたメソッドで処理が指定されたコマンドと同じです。 コマンド ハンドラー メンバー関数は、パラメーターを受け取らないし、返す**void**です。 マクロでは、次の形式があります。

```cpp
ON_COMMAND(id, memberFxn)
```

コマンド更新メッセージは同様のメカニズムを通じて行われますが、ON_UPDATE_COMMAND_UI マクロを代わりに使用します。 コマンド更新ハンドラー メンバー関数は、1 つのパラメーターへのポインターを受け取る、 [CCmdUI](../mfc/reference/ccmdui-class.md)オブジェクト、および返す**void**です。 マクロは、フォーム

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

上級ユーザーは、コマンド メッセージ ハンドラーの拡張の形式である ON_COMMAND_EX マクロを使用できます。 マクロは、ON_COMMAND 機能のスーパー セットを提供します。 拡張のコマンド ハンドラー メンバー関数は、単一のパラメーターを受け取る、 **UINT**コマンド ID が含まれていますを返す、 **BOOL**です。 戻り値にする必要があります**TRUE**コマンドが処理されていることを示すためにします。 それ以外の場合、ルーティングは、他のコマンド ターゲット オブジェクトに続行されます。

これらの形式の例:

- 内側の Resource.h (通常は Visual C によって生成される)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- クラスの宣言内

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- メッセージ マップの定義内

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- 実装ファイル

    ```cpp
    void CMyClass::OnMyCommand()
    {
        // handle the command
    }

    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)
    {
        // set the UI state with pCmdUI
    }

    BOOL CMyClass::OnComplexCommand(UINT nID)
    {
        // handle the command
        return TRUE;
    }
    ```

 上級ユーザーは 1 つのコマンド ハンドラーを使用してさまざまなコマンドを処理することができます: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)または ON_COMMAND_RANGE_EX です。 これらのマクロの詳細については、製品ドキュメントを参照してください。

> [!NOTE]
> ClassWizard が ON_COMMAND と ON_UPDATE_COMMAND_UI ハンドラーの作成をサポートしますが、ON_COMMAND_EX または ON_COMMAND_RANGE ハンドラーの作成をサポートしていません。 ただし、クラス ウィザードは解析され、4 つのコマンド ハンドラーのすべてのバリエーションを参照できるようにします。

## <a name="control-notification-messages"></a>コントロールの通知メッセージ

子コントロールから、ウィンドウに余分なビットがそのメッセージで送信されるメッセージ マップ エントリ: コントロールの id。 メッセージ マップ エントリで指定されたメッセージ ハンドラーは、次の条件に当てはまる場合にのみ呼び出されます。

- コントロール通知コード (の上位ワード*lParam*)、BN_CLICKED などのメッセージ マップ エントリに指定された通知のコードに一致します。

- コントロールの ID (*wParam*) メッセージ マップ エントリで指定されたコントロール ID と一致します。

カスタム コントロールの通知メッセージが使用して、 [ON_CONTROL](reference/message-map-macros-mfc.md#on_control)マクロをカスタムの通知コードとメッセージ マップ エントリを定義します。 このマクロには、フォーム

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

高度な使用の[ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)同じハンドラーを持つコントロールの範囲から特定のコントロールの通知を処理するために使用できます。

> [!NOTE]
> ClassWizard では、ユーザー インターフェイスで ON_CONTROL または ON_CONTROL_RANGE ハンドラーを作成することはできません。 テキスト エディターを使って手動で入力する必要があります。 ClassWizard では、これらのエントリが解析され、その他のメッセージ マップ エントリと同様に参照できます。

Windows コモン コントロールを使用して、強力な[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)の複雑なコントロール通知します。 このバージョンの MFC では、この新しいメッセージを直接サポートが ON_NOTIFY メッセージと ON_NOTIFY_RANGE マクロを使用します。 これらのマクロの詳細については、製品ドキュメントを参照してください。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)  
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)  
