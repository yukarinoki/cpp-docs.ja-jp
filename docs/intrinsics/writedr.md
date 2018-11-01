---
title: __writedr
ms.date: 11/04/2016
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: f8049485d40185d83ed01c91ad336e83f3e79834
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651816"
---
# <a name="writedr"></a>__writedr

指定されたデバッグ登録するには、指定した値を書き込みます。

## <a name="syntax"></a>構文

```
void __writedr(unsigned DebugRegister, unsigned DebugValue);
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);
```

#### <a name="parameters"></a>パラメーター

*DebugRegister*<br/>
[in]デバッグを識別する 0 ~ 7 の数値を登録します。

*DebugValue*<br/>
[in]デバッグ用に記述する値を登録します。

## <a name="remarks"></a>Remarks

これらの組み込みはカーネル モードでのみ使用できますし、ルーチンは組み込みとしてのみ使用できます。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writedr`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__readdr](../intrinsics/readdr.md)