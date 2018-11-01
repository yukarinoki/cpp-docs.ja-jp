---
title: __svm_stgi
ms.date: 11/04/2016
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 9f7e35bbecf4051e4a47c32753b3a221dd2a4cc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494667"
---
# <a name="svmstgi"></a>__svm_stgi

**Microsoft 固有の仕様**

グローバル割り込みフラグを設定します。

## <a name="syntax"></a>構文

```
void __svm_stgi(void);
```

## <a name="remarks"></a>Remarks

`__svm_stgi` 関数は `STGI` マシン語命令と同じです。 グローバル割り込みフラグは、マイクロプロセッサについて、無視、延期、または I/O の完了、ハードウェアの温度アラート、またはデバッグ例外などのイベントが原因の割り込み処理のでかどうかを判断します。

この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2: システム プログラミングでは、"ドキュメント番号 24593、3.11、リビジョン、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/)サイト。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__svm_stgi`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_clgi](../intrinsics/svm-clgi.md)