---
description: '詳細については、次を参照してください: テクニカルノート 41: MFC/OLE1 からから MFC への移行/OLE 2'
title: 'テクニカルノート 41: MFC-OLE1 からから MFC への移行-OLE 2'
ms.date: 10/18/2018
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
ms.openlocfilehash: 83bb9869d61ca9d2c92780fc6bed55ce3c3ff798
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215379"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>テクニカル ノート 41: MFC/OLE1 から MFC/OLE 2 への移植

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

## <a name="general-issues-relating-to-migration"></a>移行に関連する一般的な問題

MFC 2.5 (およびそれ以降) の OLE 2 クラスの設計目標の1つは、OLE 1.0 サポートのために MFC 2.0 に配置されているのと同じアーキテクチャの多くを保持することでした。 その結果、MFC 2.0 の同じ OLE クラスの多くが、このバージョンの MFC (、、、) に存在し `COleDocument` `COleServerDoc` `COleClientItem` `COleServerItem` ます。 また、これらのクラスの Api の多くはまったく同じです。 ただし、ole 2 が OLE 1.0 と大幅に異なるため、一部の詳細が変更されていることを期待できます。 MFC 2.0 の OLE1 からサポートに精通している場合は、MFC の2.0 サポートをご利用いただけます。

既存の MFC/OLE1 からアプリケーションを使用して OLE 2 機能を追加する場合は、まずこのメモをお読みください。 このノートでは、OLE1 から機能を MFC/OLE 2 に移植する際に発生する可能性のある一般的な問題について説明した後、mfc 2.0 に含まれる2つのアプリケーション (MFC OLE サンプルの [OCLIENT](../overview/visual-cpp-samples.md) および [HIERSVR](../overview/visual-cpp-samples.md)) を移植するときに発生する問題について説明します。

## <a name="mfc-documentview-architecture-is-important"></a>MFC のドキュメント/ビューアーキテクチャが重要

アプリケーションで MFC のドキュメント/ビューアーキテクチャを使用せず、OLE 2 サポートをアプリケーションに追加する必要がある場合は、今度はドキュメント/ビューに移動します。 MFC の OLE 2 クラスの利点の多くは、アプリケーションで MFC の組み込みアーキテクチャとコンポーネントを使用した場合にのみ実現されます。

MFC アーキテクチャを使用せずにサーバーまたはコンテナーを実装することは可能ですが、推奨されません。

## <a name="use-mfc-implementation-instead-of-your-own"></a>独自の実装ではなく、MFC の実装を使用する

MFC の "組み込みの実装" クラス `CToolBar` (、、など) には、 `CStatusBar` `CScrollView` OLE 2 サポート用の特殊なケースコードが組み込まれています。 そのため、これらのクラスをアプリケーションで使用できる場合は、それらのクラスを使用して OLE 対応にすることでメリットが得られます。 ここでも、これらの目的のために "独自の" クラスを作成することはできますが、推奨されません。 同様の機能を実装する必要がある場合、MFC ソースコードは、OLE のより詳細なポイント (特にインプレースアクティベーションの場合) を処理するための優れた参照です。

## <a name="examine-the-mfc-sample-code"></a>MFC のサンプルコードを確認する

OLE 機能を含む MFC のサンプルがいくつかあります。 これらの各アプリケーションは、さまざまな角度から OLE を実装します。

- [HIERSVR](../overview/visual-cpp-samples.md) ほとんどの場合、サーバーアプリケーションとして使用します。 Mfc/OLE1 からアプリケーションとして mfc 2.0 に含まれており、MFC/OLE 2 に移植されており、OLE 2 で利用できる多くの OLE 機能を実装するように拡張されています。

- [OCLIENT](../overview/visual-cpp-samples.md) これはスタンドアロンのコンテナーアプリケーションであり、コンテナーの観点から OLE 機能の多くを示すことを目的としています。 また、MFC 2.0 から移植され、さらに高度な OLE 機能 (カスタムクリップボード形式や埋め込みアイテムへのリンクなど) の多くをサポートするように拡張されています。

- [DRAWCLI](../overview/visual-cpp-samples.md) このアプリケーションは、既存のオブジェクト指向の描画プログラムのフレームワーク内で行われる点を除いて、OCLIENT と同様の OLE コンテナーサポートを実装します。 OLE コンテナーのサポートを実装し、既存のアプリケーションに統合する方法について説明します。

- [スーパーパッド](../overview/visual-cpp-samples.md) このアプリケーションは、スタンドアロンのアプリケーションとしても、OLE サーバーでもあります。 が実装するサーバーサポートは、最小限のものです。 特に重要なのは、OLE クリップボードサービスを使用してクリップボードにデータをコピーする方法ですが、Windows の "編集" コントロールに組み込まれている機能を使用してクリップボードの貼り付け機能を実装する方法です。 これは、従来の Windows API の使用と、新しい OLE Api との統合の興味深い組み合わせを示しています。

サンプルアプリケーションの詳細については、「MFC のサンプルヘルプ」を参照してください。

## <a name="case-study-oclient-from-mfc-20"></a>ケーススタディ: 2.0 からの OCLIENT

前述のように、 [OCLIENT](../overview/visual-cpp-samples.md) は mfc 2.0 に含まれており、MFC/ole1 からと共に OLE が実装されていました。 このアプリケーションを最初に MFC/OLE 2 クラスを使用するように変換した手順を以下に示します。 MFC/OLE クラスの説明を改善するために、初期ポートの完了後にいくつかの機能が追加されました。 これらの機能については、ここでは説明しません。これらの高度な機能の詳細については、サンプルを参照してください。

> [!NOTE]
> コンパイラエラーとステップバイステップのプロセスは Visual C++ 2.0 で作成されました。 特定のエラーメッセージと場所が Visual C++ 4.0 で変更された可能性がありますが、概念情報は有効なままです。

### <a name="getting-it-up-and-running"></a>準備と実行

OCLIENT サンプルを MFC/OLE に移植する方法は、最初にビルドして、結果として得られる明らかなコンパイラエラーを修正することから始めます。 OCLIENT サンプルを MFC 2.0 から取得し、このバージョンの MFC でコンパイルすると、解決する必要のあるエラーが多くないことがわかります。 発生した順序でのエラーについては、以下で説明します。

### <a name="compile-and-fix-errors"></a>コンパイルと修正エラー

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

最初のエラーの問題 `COleClientItem::Draw` 。 MFC/OLE1 からでは、MFC/OLE のバージョンよりも多くのパラメーターを取得していました。 多くの場合、余分なパラメーターは必要ではなく、通常は NULL です (この例では)。 このバージョンの MFC では、描画されている CDC がメタファイル DC の場合、lpWBounds の値を自動的に決定できます。 また、pFormatDC パラメーターは必要なくなりました。これは、フレームワークが、渡された pDC の "属性 DC" から1つを構築するためです。 この問題を解決するには、単に2つの余分な NULL パラメーターを描画呼び出しに単純に削除します。

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

上記のエラーは、 `COleClientItem::CreateXXXX` MFC/ole1 からのすべての関数が、アイテムを表すために一意の名前を渡す必要があるという事実から得られます。 これは、基になる OLE API の要件でした。 OLE 2 では、基になる通信機構として DDE が使用されないため (名前は DDE メッセージ交換で使用されていたため)、MFC/OLE 2 ではこれは必要ありません。 この問題を解決するには、 `CreateNewName` 関数とその関数へのすべての参照を削除します。 このバージョンでは、各 MFC/OLE 関数がどのようなことを想定しているかを簡単に確認できます。そのためには、カーソルを呼び出しに置き、F1 キーを押します。

大きな別の領域として、OLE 2 のクリップボード処理があります。 OLE1 からでは、Windows クリップボード Api を使用してクリップボードを操作しています。 OLE 2 では、別のメカニズムを使用して実行します。 MFC/OLE1 から Api では、クリップボードにオブジェクトをコピーする前に、クリップボードが開いていると想定して `COleClientItem` います。 これは不要になったため、すべての MFC/OLE クリップボード操作が失敗します。 の依存関係を削除するコードを編集している間に、 `CreateNewName` Windows クリップボードを開いて閉じるコードも削除する必要があります。

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

これらのエラーは、ハンドラーによって発生 `CMainView::OnInsertObject` します。 [新しいオブジェクトの挿入] コマンドを処理することは、非常に重要な変更点があるもう1つの領域です。 この場合、新しい OLE コンテナーアプリケーションに対して AppWizard によって提供されるのと同じ実装を簡単にマージできます。 実際、これは他のアプリケーションの移植に適用できる手法です。 MFC/OLE1 からでは、関数を呼び出すことによって、[オブジェクトの挿入] ダイアログボックスが表示され `AfxOleInsertDialog` ます。 このバージョンでは、ダイアログオブジェクトを構築し、を `COleInsertObject` 呼び出し `DoModal` ます。 また、新しい OLE 項目は classname 文字列ではなく **CLSID** で作成されます。 最終的な結果は次のようになります。

```cpp
COleInsertDialog dlg;
if (dlg.DoModal() != IDOK)
    return;

BeginWaitCursor();

CRectItem* pItem = NULL;
TRY
{
    // First create the C++ object
    pItem = GetDocument()->CreateItem();
    ASSERT_VALID(pItem);

    // Initialize the item from the dialog data.
    if (!dlg.CreateItem(pItem))
        AfxThrowMemoryException();
            // any exception will do
    ASSERT_VALID(pItem);

    // run the object if appropriate
    if (dlg.GetSelectionType() == COleInsertDialog::createNewItem)
        pItem->DoVerb(OLEIVERB_SHOW, this);

    // update right away
    pItem->UpdateLink();
    pItem->UpdateItemRectFromServer();

    // set selection to newly inserted item
    SetSelection(pItem);
    pItem->Invalidate();
}
CATCH (CException, e)
{
    // clean up item
    if (pItem != NULL)
        GetDocument()->DeleteItem(pItem);

    AfxMessageBox(IDP_FAILED_TO_CREATE);
}
END_CATCH

EndWaitCursor();
```

> [!NOTE]
> [新しいオブジェクトの挿入] は、アプリケーションによって異なる場合があります):

また \<afxodlgs.h> 、ダイアログクラスの宣言と、 `COleInsertObject` MFC によって提供されるその他の標準ダイアログを含むを含める必要があります。

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

これらのエラーは、概念上は同じであっても、一部の OLE1 から定数が OLE 2 で変更されたことが原因で発生します。 この場合、 `OLEVERB_PRIMARY` はに変更されました `OLEIVERB_PRIMARY` 。 OLE1 からと OLE 2 の両方で、ユーザーが項目をダブルクリックすると、通常、プライマリ動詞がコンテナーによって実行されます。

さらに、は、 `DoVerb` ビュー (*) へのポインターである追加のパラメーターを受け取るようになりました `CView` 。 このパラメーターは、"ビジュアル編集" (またはインプレースアクティベーション) を実装するためにのみ使用されます。 ここでは、このパラメーターを NULL に設定します。現時点ではこの機能を実装していないためです。

フレームワークがインプレースアクティブ化を試行しないようにするには、次のようにをオーバーライドする必要があり `COleClientItem::CanActivate` ます。

```cpp
BOOL CRectItem::CanActivate()
{
    return FALSE;
}
```

```Output
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function
```

MFC/OLE1 からでは、 `COleClientItem::GetBounds` と `SetBounds` は、項目の範囲を照会および操作するために使用されてい `left` ます (とメンバーは `top` 常に0です)。 MFC/OLE 2 では、この方法がとで直接サポートされています。これは、 `COleClientItem::GetExtent` `SetExtent` **サイズ** や代わりに使用 `CSize` します。

新しい SetItemRectToServer と UpdateItemRectFromServer の呼び出しのコードは次のようになります。

```cpp
BOOL CRectItem::UpdateItemRectFromServer()
{
    ASSERT(m_bTrackServerSize);
    CSize size;
    if (!GetExtent(&size))
        return FALSE;    // blank

    // map from HIMETRIC to screen coordinates
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.LPtoDP(&size);
    }
    // just set the item size
    if (m_rect.Size() != size)
    {
        // invalidate the old size/position
        Invalidate();
        m_rect.right = m_rect.left + size.cx;
        m_rect.bottom = m_rect.top + size.cy;
        // as well as the new size/position
        Invalidate();
    }
    return TRUE;
}

BOOL CRectItem::SetItemRectToServer()
{
    // set the official bounds for the embedded item
    CSize size = m_rect.Size();
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.DPtoLP(&size);
    }
    TRY
    {
        SetExtent(size);    // may do a wait
    }
    CATCH(CException, e)
    {
        return FALSE;  // links will not allow SetBounds
    }
    END_CATCH
    return TRUE;
}
```

```Output
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function
```

OLE1 からは、多くの場合、OLE1 からは本質的に非同期であるため、コンテナーからサーバーへの同期 API 呼び出しが *シミュレート* されました。 ユーザーからのコマンドを処理する前に、進行中の未処理の非同期呼び出しを確認する必要がありました。 MFC/OLE1 からには、そのための関数が用意されてい `COleClientItem::InWaitForRelease` ます。 MFC/OLE 2 では、これは必要ではないため、CMainFrame 内の OnCommand のオーバーライドをすべて削除できます。

この時点で、OCLIENT はをコンパイルしてリンクします。

### <a name="other-necessary-changes"></a>その他の必要な変更

ただし、OCLIENT では実行されないものがいくつかあります。 後ではなく、これらの問題を修正することをお勧めします。

まず、OLE ライブラリを初期化する必要があります。 これは、からを呼び出すことによって行われ `AfxOleInit` `InitInstance` ます。

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

また、パラメーターリストの変更について仮想関数を確認することもお勧めします。 このような関数の1つは `COleClientItem::OnChange` 、すべての MFC/OLE コンテナーアプリケーションでオーバーライドされます。 オンラインヘルプを見ると、余分な "DWORD dwParam" が追加されていることがわかります。 新しい CRectItem:: OnChange は次のようになります。

```cpp
void
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)
{
    if (m_bTrackServerSize && !UpdateItemRectFromServer())
    {
        // Blank object
        if (wNotification == OLE_CLOSED)
        {
            // no data received for the object - destroy it
            ASSERT(!IsVisible());
            GetDocument()->DeleteItem(this);
            return; // no update (item is gone now)
        }
    }
    if (wNotification != OLE_CLOSED)
        Dirty();
    Invalidate();
    // any change will cause a redraw
}
```

MFC/OLE1 からでは、コンテナーアプリケーションはからドキュメントクラスを派生 `COleClientDoc` しています。 MFC/OLE 2 では、このクラスは削除され、に置き換えられました `COleDocument` (この新しい組織では、コンテナー/サーバーアプリケーションを簡単に作成できます)。 にマップされる **#define** によっ `COleClientDoc` て、 `COleDocument` ole1 からアプリケーションを mfc/OLE 2 (OCLIENT など) に簡単に移植できます。 によって提供されていない機能の1つ `COleDocument` `COleClientDoc` は、標準のコマンドメッセージマップエントリです。 これは、(間接的に) も使用するサーバーアプリケーションが、 `COleDocument` コンテナー/サーバーアプリケーションでない限り、これらのコマンドハンドラーのオーバーヘッドを保持しないようにするためです。 CMainDoc メッセージマップに次のエントリを追加する必要があります。

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

これらのコマンドのすべての実装は `COleDocument` 、ドキュメントの基本クラスであるに含まれています。

この時点で、OCLIENT は機能している OLE コンテナーアプリケーションです。 任意の型 (OLE1 からまたは OLE 2) の項目を挿入することができます。 インプレースライセンス認証を有効にするために必要なコードは実装されていないため、項目は OLE1 からと同じように、別のウィンドウで編集されます。 次のセクションでは、埋め込み先編集を可能にするために必要な変更について説明します ("ビジュアル編集" とも呼ばれます)。

### <a name="adding-visual-editing"></a>"ビジュアル編集" の追加

OLE の最も興味深い機能の1つは、インプレースアクティブ化 (または "ビジュアル編集") です。 この機能により、サーバーアプリケーションはコンテナーのユーザーインターフェイスの一部を引き継ぐことができるため、よりシームレスな編集インターフェイスをユーザーに提供できます。 OCLIENT のインプレースアクティブ化を実装するには、いくつかの特別なリソースと追加のコードを追加する必要があります。 これらのリソースとコードは通常、AppWizard によって提供されます。実際、ここでのコードの多くは、"コンテナー" をサポートする新しい AppWizard アプリケーションから直接使用されていました。

まず、埋め込み先のアクティブな項目があるときに使用するメニューリソースを追加する必要があります。 この追加のメニューリソースは、IDR_OCLITYPE リソースをコピーし、ファイルとウィンドウのポップアップを除くすべてを削除することによって Visual C++ で作成できます。 グループの分離を示すために、ファイルとウィンドウのポップアップの間に2つの区切り記号が挿入されます (ファイル &#124;&#124; ウィンドウのようになります)。 これらの区切り記号の意味およびサーバーとコンテナーのメニューの結合方法の詳細については、「 [メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)」を参照してください。

これらのメニューを作成したら、フレームワークにそのことを知らせる必要があります。 これを行うには、この `CDocTemplate::SetContainerInfo` ドキュメントテンプレートを、InitInstance のドキュメントテンプレートリストに追加する前に、を呼び出します。 ドキュメントテンプレートを登録するための新しいコードは次のようになります。

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

IDR_OLECLITYPE_INPLACE リソースは、Visual C++ で作成された特殊なインプレースリソースです。

インプレースアクティベーションを有効にするには、 `CView` (CMainView) 派生クラスと `COleClientItem` 派生クラス (CRectItem) の両方で変更する必要があるものがいくつかあります。 これらのすべてのオーバーライドは AppWizard によって提供され、ほとんどの実装は既定の AppWizard アプリケーションから直接取得されます。

このポートの最初の手順では、をオーバーライドすることによって、インプレースアクティブ化が完全に無効になりました `COleClientItem::CanActivate` 。 インプレースライセンス認証を許可するには、このオーバーライドを削除する必要があります。 また、に対するすべての呼び出しに NULL が渡されました `DoVerb` (2 つがあります)。これは、ビューを提供することがインプレースアクティベーションにのみ必要だったためです。 インプレースアクティベーションを完全に実装するには、呼び出しで正しいビューを渡す必要が `DoVerb` あります。 これらの呼び出しの1つは、 `CMainView::OnInsertObject` 次のとおりです。

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

もう1つは `CMainView::OnLButtonDblClk` 次のとおりです。

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

をオーバーライドする必要が `COleClientItem::OnGetItemPosition` あります。 これにより、項目が埋め込み先でアクティブになったときに、コンテナーのウィンドウに相対的にウィンドウを配置する場所がサーバーに指示されます。 OCLIENT の場合、実装は簡単です。

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

ほとんどのサーバーでは、"埋め込み先のサイズ変更" と呼ばれるものも実装しています。 これにより、ユーザーが項目を編集しているときに、サーバーウィンドウのサイズを変更したり、移動したりできます。 ウィンドウの移動またはサイズ変更は通常、コンテナードキュメント内の位置とサイズに影響するため、コンテナーはこのアクションに参加する必要があります。 OCLIENT の実装では、m_rect によって維持される内部の四角形を新しい位置とサイズに同期します。

```cpp
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)
{
    ASSERT_VALID(this);

    if (!COleClientItem::OnChangeItemPosition(rectPos))
        return FALSE;

    Invalidate();
    m_rect = rectPos;
    Invalidate();
    GetDocument()->SetModifiedFlag();

    return TRUE;
}
```

この時点では、項目をアクティブにするためのコードが十分にあり、アクティブなときに項目のサイズを変更して移動することができますが、ユーザーが編集セッションを終了することを許可するコードはありません。 一部のサーバーでは、エスケープキーを処理することによってこの機能を提供しますが、項目を非アクティブ化するには (1) 項目の外側をクリックし、(2) エスケープキーを押すという2つの方法が用意されていることをお勧めします。

ESC キーの場合は、VK_ESCAPE キーをコマンドにマップする Visual C++ を持つアクセラレータを追加します。これにより、ID_CANCEL_EDIT がリソースに追加されます。 このコマンドのハンドラーは次のようになります。

```cpp
// The following command handler provides the standard
// keyboard user interface to cancel an in-place
// editing session.void CMainView::OnCancelEdit()
{
    // Close any in-place active item on this view.
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->Close();
    ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);
}
```

ユーザーが項目の外側をクリックした場合に対処するには、の先頭に次のコードを追加し `CMainView::SetSelection` ます。

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

アイテムがアクティブになっている場合は、フォーカスがあります。 ビューがフォーカスを受け取ると常にフォーカスがアクティブな項目に転送されるように、OnSetFocus を処理するかどうかを確認するには、次のようにします。

```cpp
// Special handling of OnSetFocus and OnSize are required
// when an object is being edited in-place.
void CMainView::OnSetFocus(CWnd* pOldWnd)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);

    if (pActiveItem != NULL &&
        pActiveItem->GetItemState() == COleClientItem::activeUIState)
    {
        // need to set focus to this item if it is same view
        CWnd* pWnd = pActiveItem->GetInPlaceWindow();
        if (pWnd != NULL)
        {
            pWnd->SetFocus();   // don't call the base class
            return;
        }
    }

    CView::OnSetFocus(pOldWnd);
}
```

ビューのサイズを変更する場合は、クリッピング四角形が変更されたことをアクティブ項目に通知する必要があります。 これを行うには、次のハンドラーを指定し `OnSize` ます。

```cpp
void CMainView::OnSize(UINT nType, int cx, int cy)
{
    CView::OnSize(nType, cx, cy);
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->SetItemRects();
}
```

## <a name="case-study-hiersvr-from-mfc-20"></a>ケーススタディ: MFC 2.0 からの HIERSVR

また、 [HIERSVR](../overview/visual-cpp-samples.md)は mfc 2.0 に含まれており、OLE と MFC/ole1 からが実装されています。 このメモでは、MFC/OLE 2 クラスを使用するために最初にこのアプリケーションを変換した手順について簡単に説明します。 MFC/OLE 2 クラスの説明を改善するために、初期ポートの完了後にいくつかの機能が追加されました。 これらの機能については、ここでは説明しません。これらの高度な機能の詳細については、サンプルを参照してください。

> [!NOTE]
> コンパイラエラーとステップバイステップのプロセスは Visual C++ 2.0 で作成されました。 特定のエラーメッセージと場所が Visual C++ 4.0 で変更された可能性がありますが、概念情報は有効なままです。

### <a name="getting-it-up-and-running"></a>準備と実行

HIERSVR サンプルを MFC/OLE に移植する方法は、最初にビルドして、結果として得られる明らかなコンパイラエラーを修正することから始めます。 HIERSVR サンプルを MFC 2.0 から取得し、このバージョンの MFC でコンパイルした場合は、解決するエラーが多くないことがわかります (ただし、OCLIENT のサンプルにはよりも多くあります)。 これらのエラーは、通常、次に示す順序で発生します。

### <a name="compile-and-fix-errors"></a>コンパイルと修正エラー

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

この最初のエラーは、サーバーの機能に関する大きな問題を `InitInstance` 示しています。 OLE サーバーに必要な初期化は、おそらく、MFC/OLE1 からアプリケーションに対して実行する必要がある最も大きな変更の1つです。 最適な方法は、AppWizard が OLE サーバー用に作成したものを確認し、必要に応じてコードを変更することです。 次に、注意すべき点をいくつか示します。

OLE ライブラリを初期化するには、を呼び出す必要があります。 `AfxOleInit`

ドキュメントテンプレートオブジェクトの SetServerInfo を呼び出して、サーバーリソースハンドルと、コンストラクターで設定できないランタイムクラス情報を設定し `CDocTemplate` ます。

/Embedding がコマンドラインに存在する場合は、アプリケーションのメインウィンドウを表示しません。

ドキュメントには **GUID** が必要です。 これは、ドキュメントの種類 (128 ビット) の一意の識別子です。 AppWizard によって作成されます。したがって、新しい AppWizard で生成されるサーバーアプリケーションから新しいコードをコピーする方法を使用する場合は、そのアプリケーションから GUID を "盗む" だけで済みます。 それ以外の場合は、BIN ディレクトリ内の GUIDGEN.EXE ユーティリティを使用できます。

を `COleTemplateServer` 呼び出して、オブジェクトをドキュメントテンプレートに "接続" する必要が `COleTemplateServer::ConnectTemplate` あります。

アプリケーションをスタンドアロンで実行する場合は、システムレジストリを更新します。 この方法は、ユーザーがを移動した場合に行います。アプリケーションの EXE。新しい場所から実行すると、新しい場所を指すように Windows システム登録データベースが更新されます。

AppWizard が用に作成した内容に基づいて、これらの変更をすべて適用した後 `InitInstance` 、 `InitInstance` HIERSVR の (および関連する GUID) は次のようになります。

```cpp
// this is the GUID for HIERSVR documents
static const GUID BASED_CODE clsid =
{ 0xA0A16360L, 0xC19B, 0x101A, { 0x8C, 0xE5, 0x00, 0xDD, 0x01, 0x11, 0x3F, 0x12 } };

/////////////////////////////////////////////////////////////////////////////
// COLEServerApp initialization

BOOL COLEServerApp::InitInstance()
{
    // OLE 2 initialization
    if (!AfxOleInit())
    {
        AfxMessageBox("Initialization of the OLE failed!");
        return FALSE;
    }

    // Standard initialization
    LoadStdProfileSettings();   // Load standard INI file options

    // Register document templates
    CDocTemplate* pDocTemplate;
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,
        RUNTIME_CLASS(CServerDoc),
        RUNTIME_CLASS(CMDIChildWnd),
        RUNTIME_CLASS(CServerView));
    pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);
    AddDocTemplate(pDocTemplate);

    // create main MDI Frame window
    CMainFrame* pMainFrame = new CMainFrame;
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))
        return FALSE;
    m_pMainWnd = pMainFrame;

    SetDialogBkColor(); // gray look

    // enable file manager drag/drop and DDE Execute open
    m_pMainWnd->DragAcceptFiles();
    EnableShellOpen();

    m_server.ConnectTemplate(clsid, pDocTemplate, FALSE);
    COleTemplateServer::RegisterAll();

    // try to launch as an OLE server
    if (RunEmbedded())
    {
        // "short-circuit" initialization -- run as server!
        return TRUE;
    }
    m_server.UpdateRegistry();
    RegisterShellFileTypes();

    // not run as OLE server, so show the main window
    if (m_lpCmdLine[0] == '\0')
    {
        // create a new (empty) document
        OnFileNew();
    }
    else
    {
        // open an existing document
        OpenDocumentFile(m_lpCmdLine);
    }

    pMainFrame->ShowWindow(m_nCmdShow);
    pMainFrame->UpdateWindow();

    return TRUE;
}
```

上記のコードでは、新しいリソース ID IDR_HIERSVRTYPE_SRVR_EMB が参照されていることがわかります。 これは、別のコンテナーに埋め込まれているドキュメントが編集されるときに使用されるメニューリソースです。 MFC/OLE1 からでは、埋め込み項目の編集に固有のメニュー項目が即座に変更されました。 ファイルベースのドキュメントを編集するのではなく、埋め込み項目を編集するときに、まったく異なるメニュー構造を使用すると、これら2つの個別のモードに対して異なるユーザーインターフェイスをより簡単に提供できます。 後で説明するように、埋め込みオブジェクトを埋め込み先で編集する場合は、完全に独立したメニューリソースが使用されます。

このリソースを作成するには、リソーススクリプトを Visual C++ に読み込んで、既存の IDR_HIERSVRTYPE メニューリソースをコピーします。 新しいリソースの名前を IDR_HIERSVRTYPE_SRVR_EMB に変更します (これは、AppWizard が使用する名前付け規則と同じです)。 次に、[ファイルの保存] を [ファイルの更新] に変更します。コマンド ID ID_FILE_UPDATE を指定してください。 また、[ファイル名を付けて保存] を [ファイル名を付けて保存] に変更します。コマンド ID ID_FILE_SAVE_COPY_AS を指定してください。 フレームワークには、これらのコマンドの両方の実装が用意されています。

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

のオーバーライドでは、 `OnSetData` **olestatus** 型を参照しているため、いくつかのエラーが発生します。 **Olestatus** は、ole1 からがエラーを返す方法でした。 これは OLE 2 では **hresult** に変更されていますが、MFC は通常、 **hresult** をエラーを含むに変換し `COleException` ます。 この場合、のオーバーライドは不要になった `OnSetData` ため、最も簡単な方法は削除することです。

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

コンストラクターは、 `COleServerItem` 余分な ' BOOL ' パラメーターを受け取ります。 このフラグによって、オブジェクトのメモリ管理がどのように行われるかが決まり `COleServerItem` ます。 この値を TRUE に設定すると、フレームワークは、これらのオブジェクトのメモリ管理を処理します。不要になった場合は削除します。 HIERSVR では `CServerItem` `COleServerItem` 、ネイティブデータの一部として (から派生した) オブジェクトを使用するため、このフラグを FALSE に設定します。 これにより、各サーバー項目がいつ削除されるかが HIERSVR によって決定されます。

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

これらのエラーは、CServerItem でオーバーライドされていない "純粋仮想" 関数があることを意味します。 これは、OnDraw のパラメーターリストが変更されたことが原因である可能性があります。 このエラーを修正するには、次のように変更し `CServerItem::OnDraw` ます (svritem 内の宣言と同様)。

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

新しいパラメーターは '//' となります。 これにより、必要に応じて、描画のサイズを入力できます。 このサイズは、 **HIMETRIC** にある必要があります。 この場合、にこの値を入力することは便利ではないため、フレームワークはを呼び出して `OnGetExtent` エクステントを取得します。 これを機能させるには、次のものを実装する必要があり `OnGetExtent` ます。

```cpp
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect, CSize& rSize)
{
    if (dwDrawAspect != DVASPECT_CONTENT)
        return COleServerItem::OnGetExtent(dwDrawAspect, rSize);

    rSize = CalcNodeSize();
    return TRUE;
}
```

```Output
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'
```

CServerItem:: CalcNodeSize 関数では、項目のサイズが **HIMETRIC** に変換され、 *m_rectBounds* に格納されます。 ドキュメントに記載されていない '*m_rectBounds*' メンバーが `COleServerItem` 存在しません ( *m_sizeExtent* によって部分的に置き換えられていますが、OLE 2 では、このメンバーの使用方法は、ole1 からでの *m_rectBounds* とは少し異なります)。 このメンバー変数に **HIMETRIC** サイズを設定するのではなく、それを返します。 この戻り値は、以前に実装されたで使用され `OnGetExtent` ます。

```cpp
CSize CServerItem::CalcNodeSize()
{
    CClientDC dcScreen(NULL);

    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,
        m_strDescription.GetLength());
    m_sizeNode += CSize(CX_INSET * 2, CY_INSET * 2);

    // set suggested HIMETRIC size
    CSize size(m_sizeNode.cx, m_sizeNode.cy);
    dcScreen.SetMapMode(MM_HIMETRIC);
    dcScreen.DPtoLP(&size);
    return size;
}
```

CServerItem もオーバーライド `COleServerItem::OnGetTextData` します。 この関数は MFC/OLE で互換性のために残されており、別のメカニズムによって置き換えられています。 Mfc OLE サンプル [HIERSVR](../overview/visual-cpp-samples.md) の mfc 3.0 バージョンでは、をオーバーライドすることによってこの機能を実装して `COleServerItem::OnRenderFileData` います。 この基本ポートでは、この機能は重要ではないため、OnGetTextData オーバーライドを削除できます。

アドレス指定されていない svritem には、さらに多くのエラーがあります。 "実際の" エラーではありません。これは、以前のエラーによって発生したエラーだけです。

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` では、フラグがサポートされなくなりました `bIncludeNative` 。 ネイティブデータ (サーバー項目のシリアル化関数によって書き込まれたデータ) は常にコピーされるため、最初のパラメーターを削除します。 さらに、 `CopyToClipboard` は、FALSE を返す代わりにエラーが発生した場合に、例外をスローします。 CServerView:: OnEditCopy のコードを次のように変更します。

```cpp
void CServerView::OnEditCopy()
{
    if (m_pSelectedNode == NULL)
        AfxThrowNotSupportedException();

    TRY
    {
        m_pSelectedNode->CopyToClipboard(TRUE);
    }
    CATCH_ALL(e)
    {
        AfxMessageBox("Copy to clipboard failed");
    }
    END_CATCH_ALL
}
```

MFC 2.0 バージョンの HIERSVR は、同じバージョンの OCLIENT の場合よりも多くのエラーが発生しましたが、実際に変更されることはほとんどありませんでした。

この時点で、HIERSVR は OLE サーバーとしてコンパイルおよび機能しますが、次に実装されるインプレース編集機能は使用されません。

### <a name="adding-visual-editing"></a>"ビジュアル編集" の追加

このサーバーアプリケーションに "ビジュアル編集" (またはインプレースライセンス認証) を追加するには、次の点を考慮する必要があります。

- 項目がアクティブになっている場合は、特殊なメニューリソースを使用する必要があります。

- このアプリケーションにはツールバーがあるため、サーバーで使用可能なメニューコマンドに対応するために、通常のツールバーのサブセットのみを含むツールバーが必要になります (上で説明したメニューリソースと一致します)。

- から派生した新しいクラスが必要です。これには、の `COleIPFrameWnd` 組み込みのユーザーインターフェイス (から派生した CMainFrame と同様に、MDI ユーザーインターフェイスが用意されています) が用意されて `CMDIFrameWnd` います。

- これらの特別なリソースとクラスについて、フレームワークに通知する必要があります。

メニューリソースは簡単に作成できます。 Visual C++ を実行し、メニューリソース IDR_HIERSVRTYPE を IDR_HIERSVRTYPE_SRVR_IP と呼ばれるメニューリソースにコピーします。 [編集] メニューと [ヘルプ] メニューのポップアップのみが表示されるようにメニューを変更します。 [編集] メニューと [ヘルプ] メニューの間のメニューに2つの区切り記号を追加します ([Edit &#124;&#124; Help] のようになります)。 これらの区切り記号の意味と、サーバーとコンテナーのメニューの結合方法の詳細については、「メニュー [とリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)」を参照してください。

サブセットツールバーのビットマップは、"Server" オプションをオンにして、新しい AppWizard で生成されたアプリケーションからコピーすることで簡単に作成できます。 その後、このビットマップを Visual C++ にインポートできます。 ビットマップに IDR_HIERSVRTYPE_SRVR_IP の ID を指定してください。

から派生したクラスは、 `COleIPFrameWnd` サーバーサポートと共に、AppWizard で生成されたアプリケーションからもコピーできます。 両方のファイル (IPFRAME) をコピーします。CPP および IPFRAME。H を追加し、プロジェクトに追加します。 呼び出しが、 `LoadBitmap` 前の手順で作成したビットマップの IDR_HIERSVRTYPE_SRVR_IP を参照していることを確認します。

新しいリソースとクラスがすべて作成されたので、必要なコードを追加して、フレームワークがこれらを認識するようにします (また、このアプリケーションがインプレース編集をサポートしていることを認識します)。 これを行うには、関数の呼び出しにいくつかのパラメーターを追加し `SetServerInfo` `InitInstance` ます。

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

インプレースライセンス認証もサポートしている任意のコンテナーで、その場で実行できるようになりました。 しかし、コードにまだ残っている軽微なバグが1つあります。 HIERSVR では、ユーザーがマウスの右ボタンを押したときに表示されるコンテキストメニューをサポートしています。 このメニューは、HIERSVR が完全に開いている場合に機能しますが、埋め込み先の埋め込みを編集するときには機能しません。 この理由は、CServerView:: OnRButtonDown のこの1行のコードにピン留めできます。

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

への参照に注意して `AfxGetApp()->m_pMainWnd` ください。 サーバーがアクティブになっていると、メインウィンドウが表示され m_pMainWnd が設定されますが、通常は非表示になります。 さらに、このウィンドウは、サーバーが完全に開いているとき、またはスタンドアロンで実行したときに表示される MDI フレームウィンドウであるアプリケーションの *メイン* ウィンドウを参照します。 アクティブなフレームウィンドウを参照しません。これは、埋め込み先のアクティブ化がから派生したフレームウィンドウである場合です `COleIPFrameWnd` 。 インプレース編集時にも正しいアクティブウィンドウを取得するために、このバージョンの MFC では、新しい関数が追加さ `AfxGetMainWnd` れています。 通常は、ではなく、この関数を使用する必要があり `AfxGetApp()->m_pMainWnd` ます。 このコードは、次のように変更する必要があります。

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

これで、OLE サーバーの機能的なインプレースアクティブ化が最小に有効になりました。 Mfc/OLE 2 では、MFC/OLE1 からでは使用できなかった多くの機能を使用できます。 実装する機能の詳細については、HIERSVR のサンプルを参照してください。 HIERSVR で実装されている機能の一部を以下に示します。

- ズーム。コンテナーに関して実際の WYSIWYG 動作を行います。

- ドラッグアンドドロップとカスタムクリップボード形式。

- 選択内容が変更されると、コンテナーウィンドウがスクロールされます。

MFC 3.0 の HIERSVR サンプルでは、サーバーアイテムに対して若干異なるデザインも使用しています。 これにより、メモリを節約し、リンクの柔軟性を高めることができます。 バージョン2.0 の HIERSVR では、ツリー内の各ノード *は-a* `COleServerItem` です。 `COleServerItem` は、これらの各ノードに対して厳密には必要以上のオーバーヘッドを伴いますが、 `COleServerItem` アクティブな各リンクにはが必要です。 しかし、ほとんどの場合、特定の時点でアクティブなリンクはほとんどありません。 これをより効率的にするために、このバージョンの MFC の HIERSVR はからノードを分離し `COleServerItem` ます。 CServerNode とクラスの両方があり `CServerItem` ます。 `CServerItem`(から派生 `COleServerItem` ) は必要に応じてのみ作成されます。 コンテナー (またはコンテナー) が特定のノードへの特定のリンクの使用を停止すると、CServerNode に関連付けられている CServerItem オブジェクトが削除されます。 この設計は、より効率的で柔軟性に優れています。 複数の選択リンクを扱う場合は、その柔軟性があります。 この2つのバージョンの HIERSVR では複数選択がサポートされていませんが、 `COleServerItem` がネイティブデータから分離されているため、MFC 3.0 バージョンの hiersvr で追加 (およびそのような選択へのリンクのサポート) が非常に簡単になります。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
