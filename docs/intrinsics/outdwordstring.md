---
title: __outdwordstring
ms.date: 11/04/2016
f1_keywords:
- __outdwordstring
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
ms.openlocfilehash: 51cb4a97d271d6d41d39d1025e3a5d34b273cdc4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035255"
---
# <a name="outdwordstring"></a>__outdwordstring

**Microsoft 固有の仕様**

生成、`rep outsd`命令で、送信`Count`ダブルワードを開始位置として`Buffer`で指定した I/O ポートから`Port`。

## <a name="syntax"></a>構文

```
void __outdwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]データを送信するポート。

*Buffer*<br/>
[in]指定したポートを送信するデータへのポインター。

*カウント*<br/>
[in]送信するダブルワードの数。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__outdwordstring`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)