---
title: 最適化 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98275f6e0a16c6d07b66ce592eb12b9391157653
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069738"
---
# <a name="optimize"></a>optimize

実行する最適化を関数ごとに指定します。

## <a name="syntax"></a>構文

```
#pragma optimize( "[optimization-list]", {on | off} )
```

## <a name="remarks"></a>Remarks

**最適化**プラグマが関数の外に表示する必要がありますあり、プラグマが発生した後に定義されている最初の関数で有効になります。 *で*と*オフ*引数で指定されたオプションを有効にする、*最適化リスト*オンまたはオフ。

*最適化リスト*次の表に示されているパラメーターの 0 個以上にすることができます。

### <a name="parameters-of-the-optimize-pragma"></a>optimize プラグマのパラメーター

|パラメーター|最適化の種類|
|--------------------|--------------------------|
|*g*|グローバル最適化を有効にします。|
|*s*または*t*|マシン語コードの省略シーケンスまたは高速シーケンスを指定します。|
|*y*|プログラム スタックにフレーム ポインターを生成します。|

使用される同じ文字のうち、 [/O](../build/reference/o-options-optimize-code.md)コンパイラ オプション。 たとえば、次のプラグマは `/Os` コンパイラ オプションと等価です。

```
#pragma optimize( "ts", on )
```

使用して、**最適化**プラグマは、空の文字列 (**""**) ディレクティブの特殊な形式です。

使用すると、*オフ*パラメーター、ように、すべての最適化*g*、 *s*、 *t*と*y*、オフします。

使用すると、*で*パラメーターで指定したに最適化がリセットされます、 [/O](../build/reference/o-options-optimize-code.md)コンパイラ オプション。

```
#pragma optimize( "", off )
.
.
.
#pragma optimize( "", on )
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)