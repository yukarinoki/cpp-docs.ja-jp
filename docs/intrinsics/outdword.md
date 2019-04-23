---
title: __outdword
ms.date: 11/04/2016
f1_keywords:
- __outdword
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
ms.openlocfilehash: 236c4812f62cb092876b400051248425ee1b13e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034233"
---
# <a name="outdword"></a>__outdword

**Microsoft 固有の仕様**

生成、`out`ダブルワードを送信する命令`Data`ポート`Port`します。

## <a name="syntax"></a>構文

```
void __outdword(
   unsigned short Port,
   unsigned long Data
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]データを送信するポート。

*データ*<br/>
[in]送信するダブルワードします。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__outdword`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)