---
title: __outbytestring
ms.date: 11/04/2016
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: c5d99ee230780d1bfdcd104c1fcf3b3bd099fd6e
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326923"
---
# <a name="outbytestring"></a>__outbytestring

**Microsoft 固有の仕様**

生成、`rep outsb`命令で、1 つ目の送信`Count`によって示されるデータのバイト`Buffer`で指定されたポートに`Port`します。

## <a name="syntax"></a>構文

```
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]データを送信するポート。

*Buffer*<br/>
[in]指定したポートを送信するデータ。

*カウント*<br/>
[in]送信するデータのバイト数。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__outbytestring`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)