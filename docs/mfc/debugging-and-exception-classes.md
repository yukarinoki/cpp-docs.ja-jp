---
title: デバッグおよび例外クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7c88c5d12f56318bbb37a825e28c2bfcbc132d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418178"
---
# <a name="debugging-and-exception-classes"></a>デバッグおよび例外クラス

これらのクラスは、動的メモリ割り当てをデバッグし、場所、例外がスローされます、関数をキャッチする関数の例外情報を渡すことのサポートを提供します。

クラスを使用して[CDumpContext](../mfc/reference/cdumpcontext-class.md)と[CMemoryState](../mfc/reference/cmemorystate-structure.md) 」の説明に従って、デバッグを支援するために開発中に[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。 使用[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 、記事の説明に従って、実行時に、任意のオブジェクトのクラスを判別する[クラス情報にアクセスする](../mfc/accessing-run-time-class-information.md)します。 フレームワークを使用して`CRuntimeClass`特定クラスのオブジェクトを動的に作成します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

