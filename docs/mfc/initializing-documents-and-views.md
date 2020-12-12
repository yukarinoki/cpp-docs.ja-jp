---
description: '詳細情報: ドキュメントとビューの初期化'
title: ドキュメントとビューの初期化
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
ms.openlocfilehash: ea0840faefac0ae5a8b4cee0fe3b707a92737c70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208035"
---
# <a name="initializing-documents-and-views"></a>ドキュメントとビューの初期化

ドキュメントは2つの異なる方法で作成されるため、ドキュメントクラスは両方の方法をサポートする必要があります。 最初に、ユーザーは、新しい空のドキュメントを作成できます。これには、File New コマンドを使用します。 その場合は、 [OnNewDocument](reference/cdocument-class.md#onnewdocument) クラスのメンバー関数のオーバーライドでドキュメントを初期 [化します](reference/cdocument-class.md)。 次に、[ファイル] メニューの [開く] コマンドを使用して、ファイルから内容を読み取る新しいドキュメントを作成できます。 その場合は、クラスの [Onopendocument](reference/cdocument-class.md#onopendocument) メンバー関数のオーバーライドでドキュメントを初期化し `CDocument` ます。 両方の初期化が同じである場合は、両方のオーバーライドから共通メンバー関数を呼び出すか、 `OnOpenDocument` `OnNewDocument` を呼び出してクリーンドキュメントを初期化してから、開いている操作を完了することができます。

ビューは、ドキュメントが作成された後に作成されます。 ビューの初期化に最適なタイミングは、フレームワークがドキュメント、フレームウィンドウ、およびビューの作成を完了した後です。 [CView](reference/cview-class.md)の[OnInitialUpdate](reference/cview-class.md#oninitialupdate)メンバー関数をオーバーライドすることにより、ビューを初期化できます。 ドキュメントが変更されるたびに再初期化または調整が必要な場合は、 [OnUpdate](reference/cview-class.md#onupdate)をオーバーライドできます。

## <a name="see-also"></a>関連項目

[ドキュメントとビューの初期化とクリーンアップ](initializing-and-cleaning-up-documents-and-views.md)
