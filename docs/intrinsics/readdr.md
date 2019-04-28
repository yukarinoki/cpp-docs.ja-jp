---
title: __readdr
ms.date: 11/04/2016
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 9d265fe75abaa7ad3cfd508613766cc3b600ee14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263284"
---
# <a name="readdr"></a>__readdr

指定されたデバッグ レジスタの値を読み取ります。

## <a name="syntax"></a>構文

```
unsigned         __readdr(unsigned int DebugRegister);
unsigned __int64 __readdr(unsigned int DebugRegister);
```

#### <a name="parameters"></a>パラメーター

*DebugRegister*<br/>
[in]デバッグを識別する 0 ~ 7 の定数を登録します。

## <a name="return-value"></a>戻り値

指定されたデバッグ レジスタの値。

## <a name="remarks"></a>Remarks

これらの組み込みはカーネル モードでのみ使用できますし、ルーチンは組み込みとしてのみ使用できます。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readdr`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)