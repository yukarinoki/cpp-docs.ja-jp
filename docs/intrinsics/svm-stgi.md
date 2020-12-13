---
description: '詳細については、次を参照してください: __svm_stgi'
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 8a6c7c221ed0bbf71a00685e8a0545818dd507a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336850"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Microsoft 固有の仕様**

グローバル割り込みフラグを設定します。

## <a name="syntax"></a>構文

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>解説

`__svm_stgi` 関数は `STGI` マシン語命令と同じです。 グローバル割り込みフラグは、i/o 完了、ハードウェア温度アラート、デバッグ例外などのイベントが原因で、マイクロプロセッサが割り込みを無視、延期、または処理するかどうかを決定します。

この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトの「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_stgi`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
