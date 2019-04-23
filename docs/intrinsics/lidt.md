---
title: __lidt
ms.date: 11/04/2016
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 757309603af48820a17668cfe272bbeaad9239b3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038474"
---
# <a name="lidt"></a>__lidt

**Microsoft 固有の仕様**

指定されたメモリ位置の値が割り込みの記述子テーブル レジスタ (IDTR) を読み込みます。

## <a name="syntax"></a>構文

```
void __lidt(void * Source);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ソース*|[in]IDTR にコピーされる値へのポインター。|

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__lidt`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`__lidt`関数は、`LIDT`マシン語命令、およびカーネル モードでのみ使用できます。 詳細については、ドキュメントの検索"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2。命令の参照を設定、"で、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__sidt](../intrinsics/sidt.md)