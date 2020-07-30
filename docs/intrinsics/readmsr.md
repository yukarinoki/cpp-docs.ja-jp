---
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 029119bc47d0172c7e9cc5fbf8cd20c4ee23e0f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219652"
---
# <a name="__readmsr"></a>__readmsr

**Microsoft 固有の仕様**

`rdmsr`によって指定されたモデル固有のレジスタを読み取り、 **`register`** その値を返す命令を生成します。

## <a name="syntax"></a>構文

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>パラメーター

*取引*\
から読み取るモデル固有のレジスタ。

## <a name="return-value"></a>戻り値

指定したレジスタの値。

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readmsr`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

この関数はカーネルモードでのみ使用でき、ルーチンは組み込みとしてのみ使用できます。

詳細については、AMD のドキュメントを参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
