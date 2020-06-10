---
title: デバッグおよび例外クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 6c7d1fc20556993c3c6690122786d7a767d895ad
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625934"
---
# <a name="debugging-and-exception-classes"></a>デバッグおよび例外クラス

これらのクラスは、動的メモリ割り当てのデバッグと、例外がキャッチされた関数にスローされる例外情報を関数から渡すためのサポートを提供します。

「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」で説明されているように、開発時に[CDumpContext](reference/cdumpcontext-class.md)と[CMemoryState](reference/cmemorystate-structure.md)クラスを使用してデバッグを支援します。 ランタイム[クラス情報へのアクセスに関する](accessing-run-time-class-information.md)記事で説明されているように、実行時にオブジェクトのクラスを特定するには、 [CRuntimeClass](reference/cruntimeclass-structure.md)を使用します。 フレームワークは、を使用して、 `CRuntimeClass` 特定のクラスのオブジェクトを動的に作成します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
