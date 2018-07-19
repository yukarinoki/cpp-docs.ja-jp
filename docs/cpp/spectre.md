---
title: spectre |Microsoft ドキュメント
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 153ff690b975ecb442c260fcebce73acd32d03fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422411"
---
# <a name="spectre"></a>spectre

**Microsoft 固有の仕様**

いない命令を挿入 Spectre バリアント 1 予測実行バリア関数の場合、コンパイラに指示します。

## <a name="syntax"></a>構文

> **__declspec( spectre(nomitigation) )**  

## <a name="remarks"></a>コメント

[/Qspectre](../build/reference/qspectre.md)コンパイラ オプションは、コンパイラが、分析では Spectre バリアント 1 のセキュリティの脆弱性が存在することを示します予測実行バリアの命令を挿入します。 出力される具体的な指示は、プロセッサに依存します。 これらの手順には、コードのサイズまたはパフォーマンスにほとんど影響がありますが、場合があります、コードが脆弱性の影響を受けないし、最大のパフォーマンスが必要です。

エキスパートによる分析可能性があります、関数が判断される Spectre バリアント 1 境界チェックのバイパスの障害からセーフであります。 適用することで、関数内で軽減コードの生成を抑制する場合は、`__declspec(spectre(nomitigation))`関数の宣言。

> [!CAUTION]
> **/Qspectre**バリアの予測の実行命令が重要なセキュリティ保護を提供し、パフォーマンスにほとんど影響があります。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。

## <a name="example"></a>例

`__declspec(spectre(nomitigation))` の使用例を次のコードに示します。

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

[__declspec](../cpp/declspec.md)  
[キーワード](../cpp/keywords-cpp.md)  
[/Qspectre](../build/reference/qspectre.md)  
