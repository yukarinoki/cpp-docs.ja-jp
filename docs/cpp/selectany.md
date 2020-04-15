---
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: e8ca82900ffd16264aca494950d4793029e55d9c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365600"
---
# <a name="selectany"></a>selectany

**マイクロソフト固有**

宣言されたグローバル データ項目 (変数またはオブジェクト) が pick-any COMDAT (パッケージ化された関数) であることをコンパイラに指示します。

## <a name="syntax"></a>構文

```
__declspec( selectany ) declarator
```

## <a name="remarks"></a>解説

リンク時、COMDAT の複数の定義が見つかった場合、リンカーは 1 つを選択し、残りを破棄します。 リンカー オプション[/OPT:REF](../build/reference/opt-optimizations.md) (最適化) が選択されている場合は、リンカー出力内の参照されていないデータ項目をすべて削除するために COMDAT の削除が発生します。

コンストラクター、および宣言におけるグローバル関数または静的メソッドによる代入は参照を作成しないため、/OPT:REF による削除が妨げられません。 このようなコードからの副作用は、データへの他の参照が存在しない時期によって決まりません。

動的に初期化されたグローバル オブジェクトの場合は**selectany**は、参照されていないオブジェクトの初期化コードも破棄します。

グローバル データ項目は、一度だけ EXE または DLL プロジェクトで正常に初期化できます。 **selectany**は、同じヘッダーが複数のソースファイルに現れる場合に、ヘッダーで定義されたグローバルデータを初期化する際に使用できます。 **selectany**は C コンパイラと C++ コンパイラの両方で使用できます。

> [!NOTE]
> **selectany**は、外部から見えるグローバルデータ項目の実際の初期化にのみ適用できます。

## <a name="example"></a>例

次のコードは **、selectany**属性の使用方法を示しています。

```cpp
//Correct - x1 is initialized and externally visible
__declspec(selectany) int x1=1;

//Incorrect - const is by default static in C++, so
//x2 is not visible externally (This is OK in C, since
//const is not by default static in C)
const __declspec(selectany) int x2 =2;

//Correct - x3 is extern const, so externally visible
extern const __declspec(selectany) int x3=3;

//Correct - x4 is extern const, so it is externally visible
extern const int x4;
const __declspec(selectany) int x4=4;

//Incorrect - __declspec(selectany) is applied to the uninitialized
//declaration of x5
extern __declspec(selectany) int x5;

// OK: dynamic initialization of global object
class X {
public:
X(int i){i++;};
int i;
};

__declspec(selectany) X x(1);
```

## <a name="example"></a>例

このコードは[、/OPT:ICF](../build/reference/opt-optimizations.md)リンカー オプションを使用する場合に **、selectany**属性を使用してデータ COMDAT の折りたたみを確実に行う方法を示しています。 データは**selectany**でマークされ **、const** (読み取り専用) セクションに配置する必要があることに注意してください。 読み取り専用セクションを明示的に指定する必要があります。

```cpp
// selectany2.cpp
// in the following lines, const marks the variables as read only
__declspec(selectany) extern const int ix = 5;
__declspec(selectany) extern const int jx = 5;
int main() {
   int ij;
   ij = ix + jx;
}
```

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
