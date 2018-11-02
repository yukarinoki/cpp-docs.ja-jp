---
title: プロバイダーのデバッグ
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
ms.openlocfilehash: e79719075bcd98733031abd63708bea861388cff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466219"
---
# <a name="debugging-your-provider"></a>プロバイダーのデバッグ

プロバイダーをデバッグする 2 つの方法はあります。

- プロセスでは、プロバイダーが作成される、ために、通常、OLE DB コンシューマー テンプレートと、プロバイダーにステップ インを使用して一部のコンシューマー コードを作成できます。

- Visual C に付属する ITEST ユーティリティを使用することができます。

## <a name="to-use-the-itest-utility"></a>ITEST ユーティリティを使用するには

1. プロバイダーのプロジェクトを開きます。

1. **プロジェクト** メニューのをクリックして**設定**します。

1. **プロパティ ページ**ダイアログ ボックスで、をクリックして、**デバッグ**タブ。

1. **デバッグ セッションの実行可能ファイル**ボックスで、ITEST アプリケーションを選択します。

1. ブレークポイントを設定し、通常どおりにデバッグします。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)