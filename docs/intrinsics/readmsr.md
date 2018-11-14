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
ms.openlocfilehash: 891ca43af4a81b63de39d367ea418e43811f78d0
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326408"
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