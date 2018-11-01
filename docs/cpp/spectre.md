---
title: spectre
ms.date: 1/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: 2377a3c23be1e27bfe4f2df23eb00823635fa05d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592011"
---
# <a name="spectre"></a>spectre

**Microsoft 固有の仕様**

Spectre variant 1 の予測実行バリア手順関数を挿入しないようコンパイラに指示します。

## <a name="syntax"></a>構文

> **__declspec( spectre(nomitigation) )**

## <a name="remarks"></a>Remarks

[/Qspectre](../build/reference/qspectre.md)コンパイラ オプションは、分析が Spectre variant 1 のセキュリティの脆弱性が存在することを示します予測実行バリアの命令を挿入するコンパイラ。 出力される具体的な手順については、プロセッサに依存します。 これらの手順には、コードのサイズまたはパフォーマンスに最小限の影響がありますが、ケースの場合、コードは、脆弱性の影響を受けませんし、最大のパフォーマンスが必要ですである可能性があります。

専門的な分析は、関数が安全で Spectre バリアント 1 境界チェックのバイパス欠陥のある判断可能性があります。 その場合は、適用することで、関数内での軽減策のコードの生成を抑制できます`__declspec(spectre(nomitigation))`関数の宣言。

> [!CAUTION]
> **/Qspectre**投機実行バリアの命令は、重要なセキュリティ保護を提供し、パフォーマンスにほとんど影響を与えるとします。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。

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
