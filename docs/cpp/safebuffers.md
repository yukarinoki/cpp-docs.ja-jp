---
title: safebuffers |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- safebuffers_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6590a2f210156711066fac241170103cc5a8830
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034359"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft 固有の仕様**

関数のバッファー オーバーラン セキュリティ チェックを挿入しないようにコンパイラに指示します。

## <a name="syntax"></a>構文

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Remarks

**/GS**コンパイラ オプションによって、コンパイラは、スタック上でセキュリティ チェックを挿入してバッファー オーバーランをテストします。 セキュリティ チェックの対象となるデータ構造体の型が記載されて[/GS (バッファー セキュリティ チェック)](../build/reference/gs-buffer-security-check.md)します。 バッファー オーバーランの検出の詳細については、次を参照してください。 [MSVC のセキュリティ機能](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)します。

専門家による手動コード レビューまたは外部解析によって、関数がバッファー オーバーランしないと判断される場合もあります。 その場合は、適用することで、関数のセキュリティ チェックを抑制できます、 **__declspec(safebuffers)** 関数の宣言キーワード。

> [!CAUTION]
>  バッファー セキュリティ チェックは重要なセキュリティ保護を提供し、パフォーマンスにはほとんど影響がありません。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。

## <a name="inline-functions"></a>インライン関数

A*プライマリ関数*使用できる、[インライン展開](inline-functions-cpp.md)のコピーを挿入するキーワード、*セカンダリ関数*。 場合、 **__declspec(safebuffers)** キーワードが関数に適用される、その関数のバッファー オーバーランの検出は抑制されます。 ただし、インライン展開の影響、 **__declspec(safebuffers)** キーワードが次のようにします。

たとえば、 **/GS**コンパイラ オプションが両方の関数に対して指定されたが、主な機能を指定します、 **__declspec(safebuffers)** キーワード。 セカンダリ関数のデータ構造によってセキュリティ チェックの対象となり、関数はこれらのチェックを抑制しません。 この場合、次のようになります。

- 指定、 [_ _forceinline](inline-functions-cpp.md)コンパイラの最適化に関係なく関数のインライン展開を強制的にセカンダリ関数のキーワード。

- 指定する場合でも、セキュリティ チェックが主な機能に適用もセカンダリ関数は、セキュリティ チェックの対象であるため、 **__declspec(safebuffers)** キーワード。

## <a name="example"></a>例

次のコードを使用する方法を示しています、 **__declspec(safebuffers)** キーワード。

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[inline、__inline、\__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)