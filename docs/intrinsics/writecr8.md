---
title: __writecr8 |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _writecr8
dev_langs:
- C++
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a06b34ee7d38e5c0e99181c4af81d925b681ce75
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417307"
---
# <a name="writecr8"></a>__writecr8

**Microsoft 固有の仕様**

値を書き込みます`Data`CR8 登録します。

## <a name="syntax"></a>構文

```
void writecr8( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]CR8 レジスタに書き込む値。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writecr8`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)