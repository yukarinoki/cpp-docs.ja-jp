---
title: 'TN071: MFC IOleCommandTarget の実装 |Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8d4b0f740e69b57944cb35f2213ae0fd54b511
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386289"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>テクニカル ノート 71: MFC IOleCommandTarget の実装

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

`IOleCommandTarget`オブジェクトとそのコンテナーを相互にコマンドをディスパッチ インターフェイスを使用できます。 たとえば、オブジェクトのツールバーのボタンがあるコマンドのなど`Print`、 `Print Preview`、 `Save`、 `New`、および`Zoom`します。 このようなオブジェクトの埋め込みをサポートするコンテナーのかどうか`IOleCommandTarget`オブジェクトがそのボタンを有効にしてコマンドに、ユーザーがクリックされたときに処理するためのコンテナーに転送します。 を通じてコマンドを送信することによってこの要求を行う可能性があります、コンテナー、埋め込みオブジェクト自体を印刷する場合は、`IOleCommandTarget`埋め込みオブジェクトのインターフェイス。

`IOleCommandTarget` 自動化のようなインターフェイスをサーバー上のメソッドを呼び出すクライアントによって使用されるということです。 ただしを使用して`IOleCommandTarget`の通常高価なを使用するプログラマが必要ないため、オートメーション インターフェイスを使用して呼び出しを行うオーバーヘッド`Invoke`メソッドの`IDispatch`します。

Mfc では、`IOleCommandTarget`インターフェイスは、コマンド、サーバーをディスパッチする Active ドキュメント コンテナーを許可する Active ドキュメント サーバーで使用されます。 Active ドキュメント サーバー クラス、 `CDocObjectServerItem`、MFC インターフェイス マップを使用して (を参照してください[TN038: MFC/OLE IUnknown の実装](../mfc/tn038-mfc-ole-iunknown-implementation.md)) を実装する、`IOleCommandTarget`インターフェイス。

`IOleCommandTarget` 実装されて、`COleFrameHook`クラス。 `COleFrameHook` インプレース編集コンテナーのフレーム ウィンドウの機能を実装するドキュメントに未記載の MFC クラスです。 `COleFrameHook` MFC インターフェイス マップを使用して実装することも、`IOleCommandTarget`インターフェイス。 `COleFrameHook`実装の`IOleCommandTarget`転送するための OLE コマンド`COleDocObjectItem`-Active ドキュメント コンテナーを派生します。 これにより、任意の MFC Active ドキュメント コンテナー Active ドキュメント サーバーからメッセージを受信できます。

## <a name="mfc-ole-command-maps"></a>MFC OLE コマンド マップ

MFC の開発者が利用できます`IOleCommandTarget`MFC OLE を使用してコマンドをマップします。 OLE コマンド マップとは、メッセージ マップ OLE コマンドをコマンド マップを含んでいるクラスのメンバー関数にマップする際に使用することができますようです。 この作業を行うには、処理するコマンドや OLE コマンドでは、コマンド ID の OLE コマンド グループを指定するコマンドのマップにマクロを配置します。、 [WM_COMMAND](/windows/desktop/menurc/wm-command) OLE コマンドが受信したときに送信されるメッセージ。 MFC には、標準の OLE コマンドのいくつかの定義済みマクロも提供します。 標準の OLE の一覧については、用に設計された最初のコマンドと Microsoft Office アプリケーションを使用して、docobj.h で定義されている OLECMDID 列挙型を参照してください。

OLE コマンド マップを含む MFC アプリケーションで、OLE コマンドが受信したときに、MFC は、アプリケーションの OLE コマンド マップで、要求されたコマンドのコマンド ID およびコマンド グループを検索しようとします。 一致が見つかった場合は、WM_COMMAND メッセージが要求されたコマンドの ID を持つコマンド マップを含むアプリケーションにディスパッチされます。 (の説明を参照して`ON_OLECMD`以下です)。これにより、アプリケーションにディスパッチ OLE コマンドは、MFC で WM_COMMAND メッセージに変換されます。 WM_COMMAND メッセージは、MFC 標準を使用して、アプリケーションのメッセージ マップ経由でルーティングし[コマンド ルーティング](../mfc/command-routing.md)アーキテクチャ。

メッセージのマップとは異なり、MFC OLE コマンド マップは ClassWizard でサポートされていません。 MFC 開発者 OLE コマンド マップのサポートと OLE コマンド マップ エントリを手動で追加する必要があります。 マップ時にアクティブなドキュメント WM_COMMAND メッセージ ルーティング チェーンでは任意のクラスで MFC Active ドキュメント サーバーに追加できる OLE コマンドでは、コンテナーで、インプレース アクティブです。 これらのクラスから派生した、アプリケーションのクラスを含める[CWinApp](../mfc/reference/cwinapp-class.md)、 [CView](../mfc/reference/cview-class.md)、 [CDocument](../mfc/reference/cdocument-class.md)、および[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)します。 Active ドキュメント コンテナーに OLE コマンド マップのみに追加できる、 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-クラスを派生します。 また、アクティブなドキュメントのコンテナーで WM_COMMAND メッセージのみにディスパッチされますでメッセージ マップ、 `COleDocObjectItem`-クラスを派生します。

## <a name="ole-command-map-macros"></a>OLE コマンド マップに関するマクロ

コマンド マップ機能をクラスに追加するのにには、次のマクロを使用します。

```cpp
DECLARE_OLECMD_MAP ()
```

このマクロは、コマンドのマップを含んでいるクラスの (通常は、ヘッダー ファイル) で、クラス宣言に移動します。

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*クラス*<br/>
コマンド マップを含んでいるクラスの名前。

*baseClass*<br/>
コマンド マップを含んでいるクラスの基底クラスの名前です。

このマクロは、コマンドのマップの先頭をマークします。 コマンド マップを含んでいるクラスの実装ファイルでこのマクロを使用します。

```
END_OLECMD_MAP()
```

このマクロは、コマンドのマップの最後をマークします。 コマンド マップを含んでいるクラスの実装ファイルでこのマクロを使用します。 このマクロは、必ずマクロを常に従う必要があります。

```
ON_OLECMD(pguid, olecmdid, id)
```

*pguid*<br/>
OLE コマンドのコマンド グループの GUID へのポインター。 このパラメーターは**NULL**の標準の OLE コマンド グループ。

*olecmdid*<br/>
呼び出されるコマンドの OLE コマンド ID。

*ID*<br/>
この OLE コマンドが呼び出されたときに、コマンドのマップを格納しているアプリケーションに送信される WM_COMMAND メッセージの ID。

コマンド マップでエントリを処理する OLE コマンドを追加するのに ON_OLECMD マクロを使用します。 OLE コマンドが受信されると、これらは、指定 WM_COMMAND メッセージに変換され標準 MFC のコマンド ルーティングのアーキテクチャを使用して、アプリケーションのメッセージ マップを通じてルーティングされます。

## <a name="example"></a>例

次の例では、処理するために MFC Active ドキュメント サーバーに OLE コマンド処理の機能を追加する方法を示しています、[います。](/windows/desktop/api/docobj/ne-docobj-olecmdid) OLE コマンド。 この例では、Active ドキュメント サーバーである MFC アプリケーションを生成するのには、AppWizard を使用することを前提としています。

1. `CView`-派生したクラスのヘッダー ファイルに、クラス宣言に DECLARE_OLECMD_MAP マクロを追加します。

    > [!NOTE]
    > 使用して、 `CView`-WM_COMMAND メッセージ ルーティング チェーンにある Active ドキュメント サーバーでクラスのいずれかに該当するためにクラスを派生します。

    ```cpp
    class CMyServerView : public CView
    {
    protected: // create from serialization only
        CMyServerView();
        DECLARE_DYNCREATE(CMyServerView)
        DECLARE_OLECMD_MAP()
        // . . .
    };
    ```

2. 実装ファイルで、 `CView`-派生クラスでは、必ずと END_OLECMD_MAP マクロの追加。

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. 標準の OLE print コマンドを処理するために追加、 [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd)標準印刷コマンドの OLE コマンド ID を指定するコマンドのマップにマクロと**ID_FILE_PRINT** WM_COMMAND id **ID_FILE_PRINT**は印刷コマンド ID がウィザードで生成された MFC アプリケーションで使用される標準。

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

Afxdocob.h で定義されている標準の OLE コマンド マクロのいずれかを使用できること、ON_OLECMD マクロの代わりにために注意してください。**います。** は標準の OLE コマンド id です。 ON_OLECMD_PRINT マクロでは、前に示した ON_OLECMD マクロとして同じタスクが実行されます。

コンテナー アプリケーションがこのサーバーに送信すると、**います。** コマンドを、サーバーの`IOleCommandTarget`インターフェイス、コマンド ハンドラーを印刷する MFC は、アプリケーションを印刷するサーバーにより、サーバーで呼び出されます。 上記の手順で追加された印刷コマンドを呼び出すには、Active ドキュメント コンテナーのコードは、次のようになります。

```cpp
void CContainerCntrItem::DoOleCmd()
{
    IOleCommandTarget *pCmd = NULL;
    HRESULT hr = E_FAIL;
    OLECMD ocm={OLECMDID_PRINT, 0};

    hr = m_lpObject->QueryInterface(
        IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if (FAILED(hr))
        return;

    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if (SUCCEEDED(hr) && (ocm.cmdf& OLECMDF_ENABLED))
    {
        //Command is available and enabled so call it
        COleVariant vIn;
        COleVariant vOut;
        hr = pCmd->Exec(NULL, OLECMDID_PRINT,
            OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);
        ASSERT(SUCCEEDED(hr));
    }
    pCmd->Release();
}
```

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
