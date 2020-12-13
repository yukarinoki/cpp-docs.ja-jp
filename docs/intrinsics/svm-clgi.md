---
description: '詳細については、次を参照してください: __svm_clgi'
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: d0b372e28b0b119d3576dd87b34f1edf883f1337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336861"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Microsoft 固有の仕様**

グローバル割り込みフラグをクリアします。

## <a name="syntax"></a>構文

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>解説

`__svm_clgi` 関数は `CLGI` マシン語命令と同じです。 グローバル割り込みフラグは、i/o 完了、ハードウェア温度アラート、デバッグ例外などのイベントが原因で、マイクロプロセッサが割り込みを無視、延期、または処理するかどうかを決定します。

この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトの「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_clgi`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
