---
title: __writecr0
ms.date: 11/04/2016
f1_keywords:
- _writecr0
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
ms.openlocfilehash: 8e36aa1c1e7299c1de5cba26acb8a4ae8165ad6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547148"
---
# <a name="writecr0"></a>__writecr0

**Microsoft 固有の仕様**

値を書き込みます`Data`CR0 レジスタにします。

## <a name="syntax"></a>構文

```
void writecr0( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]CR0 レジスタに書き込む値。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writecr0`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)