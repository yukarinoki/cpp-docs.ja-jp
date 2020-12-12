---
description: '詳細については、次を参照してください: check_stack プラグマ'
title: check_stack プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 55a639e22ded788bd731aad83eb7918e1006ae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300854"
---
# <a name="check_stack-pragma"></a>check_stack プラグマ

**Off** (または) が指定されている場合はスタックプローブをオフにし、 **-** **on** (または) が指定されている場合はスタックプローブを有効にするようにコンパイラに指示 **+** します。

## <a name="syntax"></a>構文

> **#pragma check_stack (** [{ **on**  |  **off** }] **)**\
> **#pragma check_stack** { **+**  |  **-** }

## <a name="remarks"></a>解説

このプラグマは、プラグマの後で定義されている最初の関数に対して効果があります。 スタック プローブは、マクロの一部でも、インラインで生成される関数の一部でもありません。

**Check_stack** プラグマに引数を指定しない場合、スタックチェックはコマンドラインで指定された動作に戻ります。 詳細については、「[コンパイラ オプション](../build/reference/compiler-options.md)」を参照してください。 `#pragma check_stack`と[/gs](../build/reference/gs-control-stack-checking-calls.md)オプションの相互作用を次の表にまとめます。

### <a name="using-the-check_stack-pragma"></a>check_stack プラグマの使用

|構文|コンパイルで<br /><br /> /Gs オプションを使用?|アクション|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` または<br /><br /> `#pragma check_stack`|はい|後続の関数のスタック チェックをオフにします|
|`#pragma check_stack( )` または<br /><br /> `#pragma check_stack`|いいえ|後続の関数のスタック チェックをオンにします|
|`#pragma check_stack(on)`<br /><br /> または `#pragma check_stack +`|はい、いいえ|後続の関数のスタック チェックをオンにします|
|`#pragma check_stack(off)`<br /><br /> または `#pragma check_stack -`|はい、いいえ|後続の関数のスタック チェックをオフにします|

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
