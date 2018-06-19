---
title: プログラムとリンケージ (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4154f0951b46b1c8badc0224845d2881cc8ad573
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32421368"
---
# <a name="program-and-linkage--c"></a>プログラムとリンケージ (C++)

C++ プログラムでは、各グローバル シンボルは 1 回だけ場合でも、プログラムは、複数の翻訳単位で構成されます。 実装ファイル (.cpp、.hpp、.cxx など) および直接または間接的にそれに含まれるすべてのヘッダーの翻訳単位で構成されます。 プログラムは、互いにリンクされている 1 つ以上の翻訳単位で構成されます。 

## <a name="linkage-vs-scope"></a>スコープとリンケージ

概念*リンケージ*翻訳単位間では、全体として (変数、型名、関数名) など、プログラム内のシンボルはグローバルの表示を参照します。 概念*スコープ*名前空間、クラス、または関数の本体などのブロック内で宣言されているシンボルを参照します。 このようなシンボル定義がスコープ内でのみ表示されます。リンケージの概念は、それらには適用されません。

## <a name="external-vs-internal-linkage"></a>内部リンケージと外部

非 const グローバル変数と既定では、free 関数は外部リンケージがあります。翻訳単位は、プログラムから表示されます。 この動作をオーバーライドするには、明示的として宣言して**静的**に宣言されている同じ翻訳単位の表示を制限します。 この意味**静的**ローカル変数に適用される場合は、その意味とは異なります。 として宣言された変数**const**既定では内部リンケージを持ちます。

## <a name="extern-constexpr-linkage"></a>Extern constexpr リンケージ

Visual Studio の以前のバージョンで、コンパイラでは、変数には、extern がマークされている場合でも constexpr 変数内部リンケージが常に指定します。 Visual Studio 2017 バージョン 15.5 では、新しいコンパイラ スイッチ (/Zc:externConstexpr) により、正しい標準準拠の動作が可能になります。 最終的にこれは既定値になります。

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

ヘッダー ファイルには、変数の宣言された extern constexpr が含まれている場合、としてマークする必要があります **__declspec(selectany)** するために正しく組み合わせる、重複して宣言します。

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="see-also"></a>関連項目

 [基本的な概念](../cpp/basic-concepts-cpp.md)