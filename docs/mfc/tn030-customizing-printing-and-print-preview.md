---
description: '詳細については、「テクニカルノート 30: 印刷と印刷プレビューのカスタマイズ」を参照してください。'
title: 'テクニカル ノート 30: 印刷と印刷プレビューのカスタマイズ'
ms.date: 06/28/2018
f1_keywords:
- vc.print
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
ms.openlocfilehash: 6fc0571b908f85b24b8a0752a00842077d537dce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215613"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>テクニカル ノート 30: 印刷と印刷プレビューのカスタマイズ

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、印刷と印刷プレビューをカスタマイズするプロセスについて説明し、で使用されるコールバックルーチンの目的、 `CView` およびのコールバックルーチンとメンバー関数について説明し `CPreviewView` ます。

## <a name="the-problem"></a>問題

MFC には、ほとんどの印刷と印刷プレビューのニーズに対応した完全なソリューションが用意されています。 ほとんどの場合、ビューを印刷してプレビューできるようにするには、追加のコードをほとんど必要としません。 ただし、開発者にとってかなりの労力を必要とする印刷を最適化する方法があります。また、一部のアプリケーションでは、特定のユーザーインターフェイス要素を印刷プレビューモードに追加する必要があります。

## <a name="efficient-printing"></a>効率的な印刷

MFC アプリケーションが標準のメソッドを使用して印刷すると、すべてのグラフィカルデバイスインターフェイス (GDI) の出力呼び出しがメモリ内メタファイルに送られます。 `EndPage`が呼び出されると、Windows は、プリンターが1ページを印刷するために必要な物理帯域ごとに1回メタファイルを再生します。 このレンダリング中に、GDI は Abort プロシージャを頻繁に照会して、続行するかどうかを判断します。 通常、abort プロシージャを使用すると、ユーザーが印刷ダイアログを使用して印刷ジョブを中止できるようにメッセージを処理できます。

残念ながら、これによって印刷プロセスが遅くなる可能性があります。 標準の手法を使用した場合よりもアプリケーションの印刷速度が速くなる必要がある場合は、手動でバンドを実装する必要があります。

## <a name="print-banding"></a>印刷の縞模様

手動で帯域を使用するには、ページごとに複数回呼び出されるように、印刷ループを再実装する必要があります (1 つの `OnPrint` バンドに1回)。 Print ループは、viewprnt の関数に実装されてい `OnFilePrint` ます。 派生クラスでは、 `CView` この関数をオーバーロードして、print コマンドを処理するためのメッセージマップエントリが print 関数を呼び出すようにします。 ルーチンをコピー `OnFilePrint` し、縞模様を実装するように印刷ループを変更します。 また、印刷機能にバンド四角形を渡して、印刷するページのセクションに基づいて描画を最適化できるようにすることもできます。

次に、 `QueryAbort` バンドの描画中にを頻繁に呼び出す必要があります。 それ以外の場合、Abort プロシージャは呼び出されず、ユーザーは印刷ジョブを取り消すことができません。

## <a name="print-preview-electronic-paper-with-user-interface"></a>印刷プレビュー: ユーザーインターフェイスを備えた電子紙

印刷プレビューは、基本的には、ディスプレイをプリンターのエミュレーションに切り替えようとします。 既定では、メインウィンドウのクライアント領域を使用して、ウィンドウ内に完全に1ページまたは2ページを表示します。 ユーザーはページの領域を拡大して、より詳細に表示することができます。 追加のサポートにより、ユーザーはプレビューモードでドキュメントを編集することもできます。

## <a name="customizing-print-preview"></a>印刷プレビューのカスタマイズ

このメモでは、印刷プレビューの変更に関する1つの側面 (プレビューモードへの UI の追加) についてのみ扱います。 その他の変更は可能ですが、このような変更はこの説明の範囲外です。

## <a name="to-add-ui-to-the-preview-mode"></a>UI をプレビューモードに追加するには

1. からビュークラスを派生させ `CPreviewView` ます。

2. 必要な UI の側面のコマンドハンドラーを追加します。

3. 視覚的な側面を表示に追加する場合は、を呼び出した後に、をオーバーライド `OnDraw` し、描画を実行し `CPreviewView::OnDraw` ます。

## <a name="onfileprintpreview"></a>OnFilePrintPreview

これは、印刷プレビューのコマンドハンドラーです。 既定の実装は次のとおりです。

```cpp
void CView::OnFilePrintPreview()
{
    // In derived classes, implement special window handling here
    // Be sure to Unhook Frame Window close if hooked.

    // must not create this on the frame. Must outlive this function
    CPrintPreviewState* pState = new CPrintPreviewState;

    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,
        RUNTIME_CLASS(CPreviewView), pState))
    {
        // In derived classes, reverse special window handling
        // here for Preview failure case

        TRACE0("Error: DoPrintPreview failed");
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);
        delete pState;  // preview failed to initialize, delete State now
    }
}
```

`DoPrintPreview` アプリケーションのメインウィンドウを非表示にします。 ステータスバーなどのコントロールバーは、pState->*Dwstates* メンバーで指定することによって保持できます (これはビットマスクであり、個々のコントロールバーのビットは AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR) によって定義されます)。 ウィンドウの pState->*nIDMainPane* は、自動的に非表示になり再表示されるウィンドウです。 `DoPrintPreview` によって、標準プレビュー UI 用のボタンバーが作成されます。 他のウィンドウを非表示にしたり表示したりするなど、特別なウィンドウ処理が必要な場合は、が呼び出される前に実行する必要があり `DoPrintPreview` ます。

既定では、印刷プレビューが完了すると、コントロールバーが元の状態に戻り、メインウィンドウが表示されます。 特別な処理が必要な場合は、のオーバーライドで実行する必要があり `EndPrintPreview` ます。 が失敗した場合は `DoPrintPreview` 、特別な処理も行います。

DoPrintPreview は次のように呼び出されます。

- プレビューツールバーのダイアログテンプレートのリソース ID。

- 印刷プレビューの印刷を実行するビューへのポインター。

- プレビュービュークラスのランタイムクラス。 これは、DoPrintPreview で動的に作成されます。

- CPrintPreviewState ポインターです。 CPrintPreviewState 構造 (または、アプリケーションの状態をさらに保持する必要がある場合は、派生構造) をフレームに作成し *ない* ことに注意してください。 DoPrintPreview はモードレスで、この構造は EndPrintPreview が呼び出されるまで保持されている必要があります。

  > [!NOTE]
  > 印刷サポートに個別のビュークラスまたはビュークラスが必要な場合は、そのオブジェクトへのポインターを2番目のパラメーターとして渡す必要があります。

## <a name="endprintpreview"></a>EndPrintPreview

これは、印刷プレビューモードを終了するために呼び出されます。 多くの場合、印刷プレビューで最後に表示されたドキュメント内のページに移動することをお勧めします。 `EndPrintPreview` アプリケーションを実行する可能性があります。 >pInfo *m_nCurPage* メンバーは最後に表示されたページ (2 ページが表示された場合は左端) であり、ポインターはユーザーが関心を持っていたページ上の場所を示すヒントです。 アプリケーションのビューの構造はフレームワークにとって不明であるため、選択したポイントに移動するコードを指定する必要があります。

を呼び出す前に、ほとんどのアクションを実行する必要があり `CView::EndPrintPreview` ます。 この呼び出しは、の効果を反転させ、 `DoPrintPreview` pView、pDC、および pInfo を削除します。

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp:: OnFilePrintSetup

これは、[印刷設定] メニュー項目にマップされている必要があります。 ほとんどの場合、実装をオーバーライドする必要はありません。

## <a name="page-nomenclature"></a>ページの用語

もう1つの問題は、ページの番号付けと順序のことです。 単純なワードプロセッサ型のアプリケーションでは、これは簡単な問題です。 ほとんどの印刷プレビューシステムでは、印刷された各ページが、ドキュメント内の1ページに対応していることを前提としています。

一般化されたソリューションを提供しようとすると、いくつかの点を考慮する必要があります。 たとえば、CAD システムがあるとします。 ユーザーには、いくつかの E サイズシートをカバーする描画があります。 E サイズ (またはサイズが小さく、スケール設定された) プロッターでは、ページ番号付けは単純なケースのようになります。 しかし、レーザープリンターでは、用紙ごとに16のサイズのページを印刷し、印刷プレビューでは "ページ" を検討しています。

入門用の段落として、印刷プレビューはプリンターのように機能します。 このため、選択されている特定のプリンターでは、どのような結果になるかをユーザーに確認できます。 各ページに印刷される画像は、ビューによって決定されます。

構造体のページ記述文字列は、ページ `CPrintInfo` ごとに1つの数値として表すことができる場合、ページ番号を表示する手段を提供します ("ページ 1" や "ページ 1-2" など)。 この文字列は、の既定の実装で使用され `CPreviewView::OnDisplayPageNumber` ます。 別の表示が必要な場合は、この仮想関数をオーバーライドして、"Sheet1, Sections A, B" のように指定することができます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
