---
description: '詳細情報: ドキュメント/ビューアーキテクチャの全体像'
title: Document-View アーキテクチャの全体像
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
ms.openlocfilehash: e4f8fc636349aaa12ee4481c7f6223c343b6d406
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169633"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>ドキュメント/ビュー アーキテクチャの全体像

ドキュメントとビューは、一般的な MFC アプリケーションでペアになっています。 データはドキュメントに格納されますが、ビューにはデータへの特権アクセスがあります。 [ドキュメントの表示] を分離すると、データの保存とメンテナンスがその表示から分離されます。

## <a name="gaining-access-to-document-data-from-the-view"></a>ビューからドキュメントデータへのアクセスを取得する

ビューはドキュメントのデータにアクセスします。 [Getdocument](reference/cview-class.md#getdocument) 関数は、ドキュメントへのポインターを返すか、ビュークラスを **`friend`** ドキュメントクラスの C++ にします。 その後、ビューはデータへのアクセスを使用してデータを取得し、描画や操作を行う準備ができたときにデータを取得します。

たとえば、ビューの [OnDraw](reference/cview-class.md#ondraw) メンバー関数から、ビューはを使用して `GetDocument` ドキュメントポインターを取得します。 次に、そのポインターを使用して `CString` 、ドキュメント内のデータメンバーにアクセスします。 このビューでは、文字列が関数に渡され `TextOut` ます。 この例のコードを確認するには、「 [ビューでの描画](drawing-in-a-view.md)」を参照してください。

## <a name="user-input-to-the-view"></a>ビューへのユーザー入力

ビューでは、データの選択または編集として、単独でマウスクリックを解釈することもできます。 同様に、キーストロークはデータ入力または編集として解釈される場合があります。 ユーザーが、テキストを管理するビューに文字列を入力したとします。 ビューはドキュメントへのポインターを取得し、ポインターを使用してドキュメントに新しいデータを渡します。このデータは、データ構造に格納されます。

## <a name="updating-multiple-views-of-the-same-document"></a>同じドキュメントの複数のビューを更新する

テキストエディターの分割ウィンドウなど、同じドキュメントの複数のビューを持つアプリケーションでは、最初に新しいデータがドキュメントに渡されます。 次に、ドキュメントの [UpdateAllViews](reference/cdocument-class.md#updateallviews) メンバー関数を呼び出します。これは、新しいデータを反映して、ドキュメントのすべてのビューを更新するように指示します。 これにより、ビューが同期されます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドキュメント/ビューアーキテクチャの利点](advantages-of-the-document-view-architecture.md)

- [ドキュメント/ビューアーキテクチャの代替手段](alternatives-to-the-document-view-architecture.md)

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](document-view-architecture.md)
