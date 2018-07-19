---
title: 'TN030: 印刷と印刷プレビューのカスタマイズ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.print
dev_langs:
- C++
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f67feaf03907cab836d83f4c6116ba1b2cbf32e7
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121064"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>テクニカル ノート 30: 印刷と印刷プレビューのカスタマイズ

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このノート印刷と印刷プレビューのカスタマイズ プロセスのおよびで使用されるコールバック ルーチンの目的について説明します`CView`コールバック ルーチンとメンバー関数の`CPreviewView`します。

## <a name="the-problem"></a>問題を

MFC では、ほとんどの印刷用の完全なソリューションが用意されていて、印刷プレビューの必要があります。 ほとんどの場合、わずかな追加のコードは、ビューを印刷してプレビューできるようにするために必要です。 ただしは重要な労力を必要とする印刷を最適化する方法があり、一部のアプリケーションは、印刷プレビュー モードに特定のユーザー インターフェイス要素を追加する必要があります。

## <a name="efficient-printing"></a>効率的な印刷

MFC アプリケーションは、標準メソッドを使用して印刷されたときに、Windows はインメモリ メタファイルすべてグラフィカル デバイス インターフェイス (GDI) の出力の呼び出しを指示します。 ときに`EndPage`が呼び出されると、Windows は 1 つのページを印刷するプリンターを必要とする各物理バンドの 1 回メタファイルを再生します。 この表示中に GDI は頻繁にかどうかは続行を確認する手順を中止を照会します。 通常、中止の手順では、ユーザーが印刷ダイアログを使用して、印刷ジョブを中止するように処理するメッセージが可能です。

残念ながら、印刷処理速度の遅いこのことができます。 場合は、アプリケーションでの印刷を行うには、標準的な技法を使用するよりも高速にする必要があります、手動縞模様を実装する必要があります。

## <a name="print-banding"></a>縞模様を印刷します。

手作業でバンド、再実装する必要あります印刷ループになるよう`OnPrint`(バンド) 1 回あたりのページごとに複数回を呼び出されます。 印刷ループの実装、 `OnFilePrint` viewprnt.cpp 内の関数。 `CView`-派生クラスでは、印刷コマンドを処理するためのメッセージ マップ エントリは、印刷関数を呼び出すように、この関数がオーバー ロードします。 コピー、`OnFilePrint`ルーチンと変更、印刷ループ縞模様を実装します。 おそらくは、バンド四角形、印刷の関数に渡す印刷されるページのセクションに基づいて図面を最適化するようにすることもできます。

次に、頻繁に呼び出す必要があります`QueryAbort`バンドの描画中にします。 それ以外の場合、中止プロシージャが呼び出されないと、ユーザーが、印刷ジョブを取り消すことができません。

## <a name="print-preview-electronic-paper-with-user-interface"></a>ユーザー インターフェイスを持つ print Preview: 電子ペーパー

印刷プレビュー、基本的には、しようとプリンターのエミュレーションを表示します。 既定では、メイン ウィンドウのクライアント領域は、ウィンドウ内に完全に 1 つまたは 2 つのページを表示するために使用します。 ユーザーは、さらに詳しく表示するページの領域にズーム インすることです。 追加のサポートと共に、ユーザーできる場合がありますもプレビュー モードでドキュメントを編集します。

## <a name="customizing-print-preview"></a>印刷プレビューのカスタマイズ

この注意は印刷プレビューの変更の 1 つにすぎません: プレビュー モードに UI を追加します。 その他の変更が可能であればには、このような変更はこの説明の対象外です。

## <a name="to-add-ui-to-the-preview-mode"></a>プレビュー モードに UI を追加するには

1. 派生ビュー クラスを`CPreviewView`です。

2. 必要なユーザー インターフェイス用のコマンド ハンドラーを追加します。

3. 表示する視覚的な側面を追加する場合の上書き`OnDraw`呼び出した後に、描画を実行して`CPreviewView::OnDraw`です。

## <a name="onfileprintpreview"></a>OnFilePrintPreview

これは、印刷プレビューのコマンド ハンドラーです。 既定の実装を示します。

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

`DoPrintPreview` アプリケーションのメイン ウィンドウが非表示にします。 コントロール バー、ステータス バーなどを保持できる、pState で指定する]-> [*dwStates*メンバー (これは、ビット マスクし、bits の個々 のコントロール バーは AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR) によって定義されます)。 ウィンドウ pState]-> [*nIDMainPane*ウィンドウは自動的に非表示し、reshown されます。 `DoPrintPreview` 標準のプレビュー UI を含むボタン バーが作成されます。 ウィンドウの特別な処理が必要な場合は、前に実行する必要がありますのある他のウィンドウを表示または非表示など`DoPrintPreview`と呼びます。

既定では、印刷プレビューを終了すると、コントロール バーに戻ります元の状態と、メイン ウィンドウに表示されます。 特別な処理が必要な場合は、オーバーライドで行う必要があります`EndPrintPreview`です。 場合`DoPrintPreview`失敗した場合も特別な処理を提供します。

呼び出すと呼びます。

- プレビュー ツールバーのダイアログ テンプレートのリソース ID です。

- 印刷プレビューの印刷を実行するビューへのポインター。

- [プレビュー] ビュー クラスのランタイム クラスです。 これは、呼び出すで動的に作成するされます。

- CPrintPreviewState のポインターです。 CPrintPreviewState 構造体 (または派生構造アプリケーションには、保存された複数の状態が必要な場合) 必要があります*いない*フレーム上に作成します。 呼び出すモードレスは、この構造体がそのときが呼び出されるまで存続する必要があります。

  > [!NOTE]
  > 印刷のサポートについては、個別のビューまたはビューのクラスが必要な場合、そのオブジェクトへのポインターは 2 番目のパラメーターとして渡されます。

## <a name="endprintpreview"></a>そのとき

これは、印刷プレビュー モードを終了する呼び出されます。 多くの場合、印刷プレビューで最後に表示されたドキュメントのページに移動する必要があります。 `EndPrintPreview` 行うには、アプリケーションの機会がします。 PInfo-> *m_nCurPage*メンバーが最後に表示された (左端の 2 つのページが表示されていた場合)、ページで、ポインターが場所 ページで、ユーザー関心を持っていたについてのヒント。 アプリケーションのビューの構造がフレームワークに認識できないため、選択したポイントに移動するコードを指定する必要があります。

ほとんどの操作を呼び出す前に実行する必要があります`CView::EndPrintPreview`です。 この呼び出しの効果を反転させます`DoPrintPreview`pView、pDC、および pInfo および削除します。

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup

これは、印刷のセットアップ メニュー項目にマップする必要があります。 ほとんどの場合、実装をオーバーライドする必要はありません。

## <a name="page-nomenclature"></a>ページの命名規則

別の問題は、ページの番号と順序です。 アプリケーションの種類は単純なワード プロセッサ、これは簡単です。 ほとんどのシステムで印刷プレビューでは、各印刷ページがドキュメント内の 1 つのページに対応するいると仮定します。

一般化されたソリューションを提供しようとするでは、いくつか考慮すべきことがあります。 CAD システムを想像してください。 ユーザーは、いくつかの E サイズの用紙をカバーする描画を持ちます。 E サイズで (またはより小さいスケール) プロッター、ページ番号簡単な例のようになります。 1 枚に 16 A サイズのページの印刷、レーザー プリンターで新機能は印刷プレビューを検討してください「ページ」

最初に述べたように、プリンターのように印刷プレビューが機能しています。 そのため、ユーザーは、選択されている特定のプリンターから復帰がどのような表示されます。 各ページに印刷するイメージを決定するビューの責任です。

内のページの説明文字列、`CPrintInfo`構造体は、1 ページあたり 1 つの数値として表現できる場合は、ユーザーにページ番号を表示する手段を提供 (「ページ 1」のように、または"ページ 1-2") です。 既定の実装では、この文字列を使用してください。`CPreviewView::OnDisplayPageNumber`です。 別のディスプレイが必要な場合は、たとえば、"Sheet1 セクションでは A、B"を提供する仮想関数をオーバーライドいずれかの可能性があります。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)  
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)  
