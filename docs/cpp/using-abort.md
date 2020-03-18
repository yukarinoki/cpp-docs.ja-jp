---
title: abort の使用
ms.date: 11/04/2016
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: e8cc7bce552acf67c0f9bf2025e0040dc051cff6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446417"
---
# <a name="using-abort"></a>abort の使用

[Abort](../c-runtime-library/reference/abort.md)関数を呼び出すと、即時終了が発生します。 初期化されたグローバルな静的オブジェクトの通常のデストラクション処理は実行されません。 また、`atexit` 関数を使用して指定されている特殊な処理も実行されません。

## <a name="see-also"></a>参照

[終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)