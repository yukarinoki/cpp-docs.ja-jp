---
description: '詳細情報: ExitInstance メンバー関数'
title: ExitInstance メンバー関数
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: a469d29c6b8dc2b822928293ee3bd083ccce95e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314725"
---
# <a name="exitinstance-member-function"></a>ExitInstance メンバー関数

クラス[CWinApp](reference/cwinapp-class.md)の[exitinstance](reference/cwinapp-class.md#exitinstance)メンバー関数は、アプリケーションのコピーが終了するたびに呼び出されます。通常は、ユーザーがアプリケーションを終了した結果として呼び出されます。

`ExitInstance`グラフィックスデバイスインターフェイス (GDI) リソースの解放やプログラムの実行中に使用されるメモリの割り当て解除など、特別なクリーンアップ処理が必要な場合は、をオーバーライドします。 ただし、ドキュメントやビューなどの標準アイテムのクリーンアップは、フレームワークによって提供され、これらのオブジェクトに固有の特別なクリーンアップを実行するための他のオーバーライド可能な関数が用意されています。

## <a name="see-also"></a>関連項目

[CWinApp: Application クラス](cwinapp-the-application-class.md)
