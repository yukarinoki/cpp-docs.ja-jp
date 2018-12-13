---
title: __outword
ms.date: 11/04/2016
f1_keywords:
- __outword
helpviewer_keywords:
- __outword intrinsic
- out instruction
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
ms.openlocfilehash: 8a34dfe8bfaedf8f6df5e6f26015eeccd67ed957
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332011"
---
# <a name="outword"></a>__outword

**Microsoft 固有の仕様**

生成、`out`という単語を送信するには、命令`Data`で指定した I/O ポートから`Port`します。

## <a name="syntax"></a>構文

```
void __outword(
   unsigned short Port,
   unsigned short Data
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]データを送信するポート。

*データ*<br/>
[in]送信するデータ。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__outword`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)