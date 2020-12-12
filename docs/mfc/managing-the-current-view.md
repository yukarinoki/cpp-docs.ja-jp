---
description: '詳細情報: 現在のビューの管理'
title: 現在のビューの管理
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
ms.openlocfilehash: 9c9acd315636ea33c52fbe63374b5afacef95247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283343"
---
# <a name="managing-the-current-view"></a>現在のビューの管理

フレームウィンドウの既定の実装の一部として、フレームウィンドウは現在アクティブなビューを追跡します。 分割ウィンドウのように、フレームウィンドウに複数のビューが含まれている場合は、現在のビューが使用中の最新のビューになります。 アクティブなビューは、Windows のアクティブウィンドウまたは現在の入力フォーカスに依存しません。

アクティブなビューが変更されると、フレームワークは、 [Onアクティブ](reference/cview-class.md#onactivateview) 化メンバー関数を呼び出すことにより、現在のビューに通知します。 ビューがアクティブ化されているかどうかを確認するには、 `OnActivateView` の *bactivate* パラメーターを調べます。 既定では、は、 `OnActivateView` アクティブ化時に現在のビューにフォーカスを設定します。 `OnActivateView`をオーバーライドすると、ビューが非アクティブ化または再アクティブ化されたときに、特別な処理を実行できます。 たとえば、アクティブビューを他の非アクティブなビューと区別するために、特別な視覚的な手掛かりを提供する場合があります。

フレームウィンドウは、コマンド [ルーティング](command-routing.md)に関するページで説明されているように、コマンドを現在の (アクティブな) ビューに転送します。

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](using-frame-windows.md)
