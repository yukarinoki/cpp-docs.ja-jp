---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: ebdbba130106ea5f9b893a9fd1d8277fd2dabdd4
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404692"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft 固有の仕様**

関数のバッファー オーバーラン セキュリティ チェックを挿入しないようにコンパイラに指示します。

## <a name="syntax"></a>構文

```
__declspec( safebuffers )
```

## <a name="remarks"></a>解説

**/Gs**コンパイラオプションにより、コンパイラはスタックにセキュリティチェックを挿入して、バッファーオーバーランをテストします。 セキュリティチェックの対象となるデータ構造の種類については、「 [/gs (バッファーセキュリティチェック)](../build/reference/gs-buffer-security-check.md)」を参照してください。 バッファーオーバーランの検出の詳細については、「 [MSVC のセキュリティ機能](https://devblogs.microsoft.com/cppblog/security-features-in-microsoft-visual-c/)」を参照してください。

専門家による手動コード レビューまたは外部解析によって、関数がバッファー オーバーランしないと判断される場合もあります。 その場合は、関数の宣言に **__declspec (safebuffers)** キーワードを適用することによって、関数のセキュリティチェックを抑制することができます。

> [!CAUTION]
> バッファー セキュリティ チェックは重要なセキュリティ保護を提供し、パフォーマンスにはほとんど影響がありません。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。

## <a name="inline-functions"></a>インライン関数

*プライマリ関数*では、[インライン展開](inline-functions-cpp.md)キーワードを使用して、*セカンダリ関数*のコピーを挿入できます。 **__Declspec (safebuffers)** キーワードが関数に適用されている場合、その関数のバッファーオーバーランの検出は抑制されます。 ただし、インライン展開は、次の方法で **__declspec (safebuffers)** キーワードに影響します。

**/Gs**コンパイラオプションが両方の関数に対して指定されているものの、プライマリ関数は **__declspec (safebuffers)** キーワードを指定しているとします。 セカンダリ関数のデータ構造によってセキュリティ チェックの対象となり、関数はこれらのチェックを抑制しません。 この場合、次のようになります。

- コンパイラの最適化に関係なく、その関数を強制的にインライン化するには、セカンダリ関数で[__forceinline](inline-functions-cpp.md)キーワードを指定します。

- セカンダリ関数はセキュリティチェックの対象であるため、セキュリティチェックは、 **__declspec (safebuffers)** キーワードを指定している場合でも、プライマリ関数にも適用されます。

## <a name="example"></a>例

次のコードは、 **__declspec (safebuffers)** キーワードを使用する方法を示しています。

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
