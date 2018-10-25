---
title: no_implementation |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_implementation
dev_langs:
- C++
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f169b30394e3fdf893475a49946266143772eb7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078064"
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