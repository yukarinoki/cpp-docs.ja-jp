---
title: __writeeflags
ms.date: 11/04/2016
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 6679a3b16def3ed413c5cec2a4bb7d5fe5d732c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389919"
---
# <a name="writeeflags"></a>__writeeflags

指定した値をプログラムに書き込みますステータスと制御 (空文) を登録します。

## <a name="syntax"></a>構文

```
void __writeeflags(unsigned Value);
void __writeeflags(unsigned __int64 Value);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*[値]*|[in]立てるレジスタに書き込む値。 `Value`パラメーターは、32 ビット、32 ビット プラットフォームの時間の長いと 64 ビット、64 ビット プラットフォームの時間の長い。|

## <a name="remarks"></a>Remarks

これらのルーチンは組み込みとしてのみ使用できます。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writeeflags`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)