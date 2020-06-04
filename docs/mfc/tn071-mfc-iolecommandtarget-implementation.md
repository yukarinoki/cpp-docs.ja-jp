---
title: 'テクニカル ノート 71: MFC IOleCommandTarget の実装'
ms.date: 06/28/2018
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
ms.openlocfilehash: 56745e7985c8af97b0b628d148586ccef346d95a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442077"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>テクニカル ノート 71: MFC IOleCommandTarget の実装

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

`IOleCommandTarget` インターフェイスは、オブジェクトとそのコンテナーがコマンドを相互にディスパッチできるようにします。 たとえば、オブジェクトのツールバーには、`Print`、`Print Preview`、`Save`、`New`、`Zoom`などのコマンドのボタンが含まれている場合があります。 このようなオブジェクトが `IOleCommandTarget`をサポートするコンテナーに埋め込まれている場合、オブジェクトは、そのボタンを有効にし、ユーザーがクリックしたときに、コンテナーにコマンドを転送して処理することができます。 コンテナーが埋め込みオブジェクトを出力する必要がある場合は、埋め込みオブジェクトの `IOleCommandTarget` インターフェイスを介してコマンドを送信することによって、この要求を行うことができます。

`IOleCommandTarget` は、クライアントがサーバーでメソッドを呼び出すために使用するという、オートメーションに似たインターフェイスです。 ただし、`IOleCommandTarget` を使用すると、プログラマは `IDispatch`の通常のコスト `Invoke` 方法を使用する必要がないため、オートメーションインターフェイスを使用して呼び出しを行うオーバーヘッドを節約できます。

MFC では、active ドキュメントサーバーが `IOleCommandTarget` インターフェイスを使用して、アクティブドキュメントコンテナーがサーバーにコマンドをディスパッチできるようにします。 Active ドキュメントサーバークラス `CDocObjectServerItem`は、MFC インターフェイスマップを使用します (「[テクニカルノート 38: mfc/OLE IUnknown の実装](../mfc/tn038-mfc-ole-iunknown-implementation.md)」を参照)。 `IOleCommandTarget` インターフェイスを実装します。

`IOleCommandTarget` は、`COleFrameHook` クラスにも実装されます。 `COleFrameHook` は、埋め込み先編集コンテナーのフレームウィンドウ機能を実装する、ドキュメントに記載されていない MFC クラスです。 また `COleFrameHook` は、MFC インターフェイスマップを使用して `IOleCommandTarget` インターフェイスを実装します。 `COleFrameHook`の実装では、`IOleCommandTarget` OLE コマンドを `COleDocObjectItem`によって派生した Active ドキュメントコンテナーに転送します。 これにより、すべての MFC アクティブドキュメントコンテナーが、含まれているアクティブなドキュメントサーバーからメッセージを受信できるようになります。

## <a name="mfc-ole-command-maps"></a>MFC OLE コマンドマップ

MFC 開発者は、MFC OLE コマンドマップを使用して `IOleCommandTarget` を利用できます。 OLE コマンドマップは、コマンドマップを含むクラスのメンバー関数に OLE コマンドをマップするために使用できるため、メッセージマップに似ています。 この作業を行うには、コマンドマップにマクロを配置して、処理するコマンドの OLE コマンドグループ、OLE コマンド、および OLE コマンドを受信したときに送信される[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージのコマンド ID を指定します。 MFC には、標準の OLE コマンド用の定義済みマクロも多数用意されています。 もともと Microsoft Office アプリケーションで使用するように設計された標準の OLE コマンドの一覧については、「OLECMDID 列挙型」を参照してください。

Ole コマンドマップを含む MFC アプリケーションによって OLE コマンドが受信されると、MFC は、アプリケーションの OLE コマンドマップで、要求されたコマンドのコマンド ID とコマンドグループを見つけようとします。 一致が見つかった場合は、要求されたコマンドの ID を持つコマンドマップを含むアプリケーションに WM_COMMAND メッセージがディスパッチされます。 (以下の `ON_OLECMD` の説明を参照してください)。このようにして、アプリケーションにディスパッチされた OLE コマンドは、MFC によって WM_COMMAND メッセージに変換されます。 WM_COMMAND メッセージは、MFC 標準の[コマンドルーティング](../mfc/command-routing.md)アーキテクチャを使用して、アプリケーションのメッセージマップを通じてルーティングされます。

メッセージマップとは異なり、MFC OLE コマンドマップは ClassWizard ではサポートされていません。 MFC 開発者は、OLE コマンドマップのサポートと OLE コマンドマップのエントリを手動で追加する必要があります。 OLE コマンドマップは、アクティブなドキュメントがコンテナー内でアクティブになっているときに、WM_COMMAND メッセージルーティングチェーン内にある任意のクラスの MFC Active ドキュメントサーバーに追加できます。 これらのクラスには、 [CWinApp](../mfc/reference/cwinapp-class.md)、 [CView](../mfc/reference/cview-class.md)、 [CDocument](../mfc/reference/cdocument-class.md)、および[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)から派生したアプリケーションのクラスが含まれます。 Active ドキュメントコンテナーでは、OLE コマンドマップは[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)派生クラスにのみ追加できます。 また、Active ドキュメントコンテナーでは、WM_COMMAND メッセージは、`COleDocObjectItem`派生クラスのメッセージマップにのみディスパッチされます。

## <a name="ole-command-map-macros"></a>OLE コマンドマップマクロ

次のマクロを使用して、コマンドマップ機能をクラスに追加します。

```cpp
DECLARE_OLECMD_MAP ()
```

このマクロは、コマンドマップを含んでいるクラスのクラス宣言 (通常はヘッダーファイル内) に格納されます。

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*クラス*<br/>
コマンドマップを含むクラスの名前。

*baseClass*<br/>
コマンドマップを含むクラスの基本クラスの名前。

このマクロは、コマンドマップの先頭をマークします。 このマクロは、コマンドマップを含むクラスの実装ファイルで使用します。

```
END_OLECMD_MAP()
```

このマクロは、コマンドマップの末尾を示します。 このマクロは、コマンドマップを含むクラスの実装ファイルで使用します。 このマクロは、常に BEGIN_OLECMD_MAP マクロに従う必要があります。

```
ON_OLECMD(pguid, olecmdid, id)
```

*pguid*<br/>
OLE コマンドのコマンドグループの GUID へのポインター。 このパラメーターは、標準の OLE コマンドグループの場合は**NULL**です。

*olecmdid*<br/>
呼び出すコマンドの OLE コマンド ID。

*id*<br/>
この OLE コマンドが呼び出されたときにコマンドマップを含むアプリケーションに送信される WM_COMMAND メッセージの ID。

コマンドマップの ON_OLECMD マクロを使用して、処理する OLE コマンドのエントリを追加します。 OLE コマンドが受信されると、これらのコマンドは、指定された WM_COMMAND メッセージに変換され、標準の MFC コマンドルーティングアーキテクチャを使用して、アプリケーションのメッセージマップを通じてルーティングされます。

## <a name="example"></a>例

次の例は、OLE コマンド処理機能を MFC Active ドキュメントサーバーに追加して[OLECMDID_PRINT](/windows/win32/api/docobj/ne-docobj-olecmdid) ole コマンドを処理する方法を示しています。 この例では、AppWizard を使用して、アクティブなドキュメントサーバーである MFC アプリケーションを生成していることを前提としています。

1. `CView`派生クラスのヘッダーファイルで、DECLARE_OLECMD_MAP マクロをクラス宣言に追加します。

    > [!NOTE]
    > WM_COMMAND メッセージルーティングチェーンにある Active ドキュメントサーバーのクラスの1つであるため、`CView`派生クラスを使用します。

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

2. `CView`派生クラスの実装ファイルで、BEGIN_OLECMD_MAP と END_OLECMD_MAP マクロを追加します。

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. 標準の OLE 印刷コマンドを処理するには、標準の print コマンドの OLE コマンド ID と WM_COMMAND ID の**ID_FILE_PRINT**を指定して、コマンドマップに[ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd)マクロを追加します。 **ID_FILE_PRINT**は、AppWizard で生成された MFC アプリケーションで使用される標準の印刷コマンド ID です。

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

Afxdocob で定義されている標準の OLE コマンドマクロの1つは、標準の OLE コマンド ID で**OLECMDID_PRINT**ため、ON_OLECMD マクロの代わりに使用できることに注意してください。 ON_OLECMD_PRINT マクロは、上に示した ON_OLECMD マクロと同じタスクを実行します。

コンテナーアプリケーションがサーバーの `IOleCommandTarget` インターフェイスを使用してこのサーバーを**OLECMDID_PRINT**コマンドに送信すると、サーバーで MFC 印刷コマンドハンドラーが呼び出され、サーバーはアプリケーションを出力します。 上記の手順で追加した印刷コマンドを呼び出すアクティブドキュメントコンテナーのコードは、次のようになります。

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

## <a name="see-also"></a>参照

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
