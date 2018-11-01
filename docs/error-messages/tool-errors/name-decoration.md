---
title: 名前の装飾
ms.date: 09/05/2018
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: c01e684be62dbb8716f8556680b1c692af1efc45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598862"
---
# <a name="name-decoration"></a>名前の装飾

名前の装飾は、通常は C++ の名前付け規則を指しますが、C の場合でもよく適用されます。 既定では、C++ では関数名、パラメーター、および戻り値の型を使用して、関数のリンカー名が作成されます。 次の関数について考えてみます。

```
void CALLTYPE test(void)
```

次の表は、さまざまな呼び出し規約のリンカー名を示します。

|呼び出し規約|extern"C"または .c ファイル|.cpp、.cxx、または /TP|
|------------------------|---------------------------|------------------------|
|C の名前付け規則 (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Fastcall 名前付け規則 (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|標準呼び出しの名前付け規則 (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vectorcall 名前付け規則 (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

C++ から C の関数を呼び出すには、extern "C" を使用します。 extern "C" を指定すると、クラスに属さない C++ の関数に対しては、C 名前付け規則が適用されます。 コンパイラ スイッチに注意してください。 **/Tc**または **/Tp**、コンパイラがファイル名拡張子を無視して、ファイルをそれぞれ C または C++ としてコンパイルするように指示します。 これらのオプションを使用すると、予測した名前にならないことがあります。

関数プロトタイプのパラメーターが一致していないと、このエラーが発生します。 名前の装飾では、関数のパラメーターを最終の装飾関数名に組み込みます。 関数宣言でのパラメーターと一致していない関数を呼び出すと、LNK2001 が発生することがあります。

現在では、コンパイラ販売元間またはコンパイラのバージョン間でさえも、C++ の名前付けの規則が確立されていません。 そのため、別のコンパイラでコンパイルされたオブジェクト ファイルをリンクすると、名前付け方式が異なり、外部参照が未解決になります。

## <a name="see-also"></a>関連項目

[リンカー ツール エラー LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)