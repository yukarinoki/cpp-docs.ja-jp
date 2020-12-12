---
description: '詳細情報: spectre'
title: spectre
ms.date: 01/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: fc1f56a59dea1eaa3596a6f7a7c0347ab822e302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113819"
---
# <a name="spectre"></a>spectre

**Microsoft 固有の仕様**

関数の Spectre variant 1 予測実行バリア命令を挿入しないようコンパイラに指示します。

## <a name="syntax"></a>構文

> **__declspec (spectre (nomitigation))**

## <a name="remarks"></a>解説

[/Qspectre](../build/reference/qspectre.md)コンパイラオプションを指定すると、コンパイラは予測実行バリア命令を挿入します。 これらは挿入されます。分析では、Spectre variant 1 セキュリティ脆弱性が存在することを示します。 出力される具体的な手順は、プロセッサによって異なります。 これらの手順は、コードのサイズやパフォーマンスに最小限の影響を与える必要がありますが、コードが脆弱性の影響を受けない場合や、最大限のパフォーマンスが必要な場合もあります。

専門家による分析では、Spectre variant 1 の境界確認のバイパスの欠陥から、関数が安全であると判断する場合があります。 その場合は、関数宣言にを適用することによって、関数内で軽減コードを生成しないようにすることができ `__declspec(spectre(nomitigation))` ます。

> [!CAUTION]
> **/Qspectre** 予測実行バリアの指示は、重要なセキュリティ保護を提供し、パフォーマンスにわずかに影響を与えます。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。

## <a name="example"></a>例

`__declspec(spectre(nomitigation))`の使用例を次のコードに示します。

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
