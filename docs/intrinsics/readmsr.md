---
title: _ _readmsr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readmsr
dev_langs:
- C++
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d21d33d1e90d7c4aac9ea833d0c5bd80f5172312
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416605"
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

## <a name="requirements"></a>要件

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