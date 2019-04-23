---
title: __sidt
ms.date: 11/04/2016
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 88dbb4713577fcf224e1c5646bf4c38b2a1dfafe
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036761"
---
# <a name="sidt"></a>__sidt

**Microsoft 固有の仕様**

指定されたメモリ位置では、割り込み記述子テーブル レジスタ (IDTR) の値を格納します。

## <a name="syntax"></a>構文

```
void __sidt(void * Destination);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Destination (公開先)*|[in]IDTR が格納されているメモリ位置へのポインター。|

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__sidt`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`__sidt` 関数は `SIDT` マシン語命令と同じです。 詳細については、ドキュメントの検索"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2。命令の参照を設定、"で、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)