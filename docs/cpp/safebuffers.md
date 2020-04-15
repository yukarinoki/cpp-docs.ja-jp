---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: bc4736ce233ce026ecab9ef38ac8379466b5a0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365586"
---
# <a name="safebuffers"></a>safebuffers

**マイクロソフト固有**

関数のバッファー オーバーラン セキュリティ チェックを挿入しないようにコンパイラに指示します。

## <a name="syntax"></a>構文

```
__declspec( safebuffers )
```

## <a name="remarks"></a>解説

**/GS**コンパイラ オプションを指定すると、スタックにセキュリティ チェックを挿入して、コンパイラがバッファ オーバーランをテストします。 セキュリティ チェックの対象となるデータ構造体の種類については[、/GS (バッファ セキュリティ チェック)](../build/reference/gs-buffer-security-check.md)を参照してください。 バッファ オーバーラン検出の詳細については、「 [MSVC のセキュリティ機能](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)」を参照してください。

専門家による手動コード レビューまたは外部解析によって、関数がバッファー オーバーランしないと判断される場合もあります。 その場合は、関数宣言に **__declspec(safebuffers)** キーワードを適用することで、関数のセキュリティ チェックを抑制できます。

> [!CAUTION]
> バッファー セキュリティ チェックは重要なセキュリティ保護を提供し、パフォーマンスにはほとんど影響がありません。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。

## <a name="inline-functions"></a>インライン関数

*1 次関数*は、[インライン](inline-functions-cpp.md)化キーワードを使用して 2*次関数*のコピーを挿入できます。 **__declspec(safebuffers)** キーワードが関数に適用されると、その関数に対するバッファ オーバーラン検出は抑制されます。 ただし、インライン化は、次の方法で **__declspec (セーフバッファ)** キーワードに影響を与えます。

両方の関数に **/GS**コンパイラ オプションが指定されているが、プライマリ関数が **__declspec(セーフバッファ)** キーワードを指定するとします。 セカンダリ関数のデータ構造によってセキュリティ チェックの対象となり、関数はこれらのチェックを抑制しません。 この場合、次のようになります。

- コンパイラの最適化に関係なく、コンパイラがその関数をインライン化するように、セカンダリ関数の[__forceinline](inline-functions-cpp.md)キーワードを指定します。

- 2 次関数はセキュリティ チェックの対象となるため **、__declspec(safebuffers)** キーワードを指定していても、プライマリ関数にもセキュリティ チェックが適用されます。

## <a name="example"></a>例

次のコードは **、__declspec (セーフバッファ)** キーワードの使用方法を示しています。

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

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[インライン, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
