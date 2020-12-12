---
description: 詳細については、「デバッグと例外クラス」を参照してください。
title: デバッグおよび例外クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 2c14ea8d51fd1b63427ad1495e711a906e013ea4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291117"
---
# <a name="debugging-and-exception-classes"></a>デバッグおよび例外クラス

これらのクラスは、動的メモリ割り当てのデバッグと、例外がキャッチされた関数にスローされる例外情報を関数から渡すためのサポートを提供します。

「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」で説明されているように、開発時に[CDumpContext](reference/cdumpcontext-class.md)と[CMemoryState](reference/cmemorystate-structure.md)クラスを使用してデバッグを支援します。 [CRuntimeClass](reference/cruntimeclass-structure.md)を使用して、実行時にオブジェクトのクラスを特定します。詳細については[Run-Time クラス情報へのアクセスに関する](accessing-run-time-class-information.md)記事を参照してください。 フレームワークは、を使用して、 `CRuntimeClass` 特定のクラスのオブジェクトを動的に作成します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
