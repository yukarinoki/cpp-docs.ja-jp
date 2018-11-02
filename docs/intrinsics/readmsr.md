---
title: __readmsr
ms.date: 11/04/2016
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 45e9c21eb8d9ac213812236a91c050c3c9df8f8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641065"
---
# <a name="readmsr"></a>__readmsr

**Microsoft 固有の仕様**

生成、`rdmsr`命令で指定されたモデルに固有のレジスタの読み取りが`register`し、その値を返します。

## <a name="syntax"></a>構文

```
__int64 __readmsr( 
   int register 
);
```

#### <a name="parameters"></a>パラメーター

*register*<br/>
[in]読み取りモデル専用レジスタ。

## <a name="return-value"></a>戻り値

指定されたレジスタの値。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readmsr`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この関数はのみカーネル モードで利用でき、ルーチンは組み込みとして使用できるのみです。

詳細については、AMD のマニュアルを参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)