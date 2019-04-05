---
title: ループ
ms.date: 10/18/2018
f1_keywords:
- loop_CPP
- vc-pragma.loop
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
ms.openlocfilehash: a1640881d98073381a941478f4b78177a95698d7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023167"
---
# <a name="loop"></a>ループ

ループのコードを自動並列化によって処理する方法を制御します。また、ループを自動ベクター化の対象から除外します。

## <a name="syntax"></a>構文

```
#pragma loop( hint_parallel(n) )
#pragma loop( no_vector )
#pragma loop( ivdep )
```

### <a name="parameters"></a>パラメーター

*hint_parallel(n)*<br/>
間で、このループを並列化する必要がありますコンパイラにヒント*n* 、スレッド、 *n*は正の整数リテラルまたはゼロです。 場合*n* 0 の場合は、スレッドの最大数は、実行時に使用されます。 これはコンパイラに対するヒントであり、ループが並列化される保証はありません。 ループにデータ間の依存関係、つまり構造上の問題 (たとえばループが、ループ本体を超えて使用されるスカラーに格納するなど) がある場合、ループは並列化されません。

コンパイラはこのオプションを無視しない限り、 [/Qpar](../build/reference/qpar-auto-parallelizer.md)コンパイラ スイッチを指定します。

*no_vector*<br/>
自動ベクター化は既定でオンになっており、必要と評価されたすべてのループのベクター化が試みられます。 このプラグマは、後続のループの自動ベクター化を無効にする場合に指定します。

*ivdep*<br/>
このループでベクターの依存関係を無視するようにコンパイラにヒントを与えます。 これを組み合わせて使用して*hint_parallel*します。

## <a name="remarks"></a>Remarks

使用する、**ループ**プラグマ、直前に配置-ではなく、ループの定義。 プラグマは後続のループのスコープ内で有効です。 1 つのループに複数のプラグマを任意の順序で適用できますが、プラグマを 1 つずつ個別のステートメントで指定する必要があります。

## <a name="see-also"></a>関連項目

[自動並行化と自動ベクター化](../parallel/auto-parallelization-and-auto-vectorization.md)<br/>
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)