---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 26527ca69c66c73f5d41084dc42df5faa34481d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409812"
---
# <a name="noimplementation"></a>no_implementation
**C++ 固有の仕様**

ラッパー メンバー関数の実装を含む .tli ヘッダーの生成を抑制します。

## <a name="syntax"></a>構文

```
no_implementation
```

## <a name="remarks"></a>Remarks

この属性を指定すると、タイプ ライブラリの項目の公開が宣言され、.tlh ヘッダーが生成されます。`#include` ステートメントによって .tli ヘッダー ファイルは取り込まれません。

この属性と組み合わせて使用[implementation_only](../preprocessor/implementation-only.md)します。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)