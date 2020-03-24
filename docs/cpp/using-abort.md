---
title: abort の使用
ms.date: 11/04/2016
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: db0f6cdcdaf4bca1b74d89a9415c4f7951455d80
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187858"
---
# <a name="using-abort"></a>abort の使用

[Abort](../c-runtime-library/reference/abort.md)関数を呼び出すと、即時終了が発生します。 初期化されたグローバルな静的オブジェクトの通常のデストラクション処理は実行されません。 また、`atexit` 関数を使用して指定されている特殊な処理も実行されません。

## <a name="see-also"></a>参照

[終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)
