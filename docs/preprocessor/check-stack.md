---
title: check_stack
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 93ded20bde98cc4e7b0fc15fd8332195d38f2543
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451988"
---
# <a name="checkstack"></a>check_stack
場合、スタック プローブをオフにするようにコンパイラに指示`off`(または`-`) が指定されているか場合は、スタック プローブを有効に`on`(または`+`) を指定します。

## <a name="syntax"></a>構文

```
#pragma check_stack([ {on | off}] )
#pragma check_stack{+ | -}
```

## <a name="remarks"></a>Remarks

引数を指定しない場合、スタック プローブが既定に従って処理されます。 このプラグマは、プラグマの後で定義されている最初の関数に対して効果があります。 スタック プローブは、マクロの一部でも、インラインで生成される関数の一部でもありません。

引数を指定しない場合、 **check_stack**プラグマ、スタック チェック コマンドラインで指定された動作を元に戻します。 詳細については、次を参照してください。[コンパイラ リファレンス](../build/reference/compiler-options.md)します。 相互作用、`#pragma check_stack`と[/Gs](../build/reference/gs-control-stack-checking-calls.md)オプションは、次の表にまとめられています。

### <a name="using-the-checkstack-pragma"></a>check_stack プラグマの使用

|構文|コンパイルで<br /><br /> /Gs オプションを使用?|アクション|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` または<br /><br /> `#pragma check_stack`|はい|後続の関数のスタック チェックをオフにします|
|`#pragma check_stack( )` または<br /><br /> `#pragma check_stack`|いいえ|後続の関数のスタック チェックをオンにします|
|`#pragma check_stack(on)`<br /><br /> または `#pragma check_stack +`|Yes または No|後続の関数のスタック チェックをオンにします|
|`#pragma check_stack(off)`<br /><br /> または `#pragma check_stack -`|Yes または No|後続の関数のスタック チェックをオフにします|

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)