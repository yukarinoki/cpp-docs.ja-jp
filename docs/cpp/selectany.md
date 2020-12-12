---
description: '詳細情報: `selectany`'
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: e17ad5787211aacbb206d5e68ba355047711b96a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319340"
---
# `selectany`

**Microsoft 固有の仕様**

宣言されたグローバル データ項目 (変数またはオブジェクト) が pick-any COMDAT (パッケージ化された関数) であることをコンパイラに指示します。

## <a name="syntax"></a>構文

> **`__declspec( selectany )`***宣言子*

## <a name="remarks"></a>解説

リンク時、COMDAT の複数の定義が見つかった場合、リンカーは 1 つを選択し、残りを破棄します。 リンカーオプション ([ [`/OPT:REF`](../build/reference/opt-optimizations.md) 最適化]) が選択されている場合、COMDAT 削除が行われ、リンカー出力内の参照されていないデータ項目がすべて削除されます。

コンストラクター、および宣言におけるグローバル関数または静的メソッドによる代入は参照を作成しないため、/OPT:REF による削除が妨げられません。 このようなコードからの副作用は、データへの他の参照が存在しない時期によって決まりません。

動的に初期化されるグローバルオブジェクトの場合は、参照 **`selectany`** されていないオブジェクトの初期化コードも破棄されます。

グローバル データ項目は、一度だけ EXE または DLL プロジェクトで正常に初期化できます。 **`selectany`** 複数のソースファイルに同じヘッダーがある場合に、ヘッダーによって定義されたグローバルデータの初期化に使用できます。 **`selectany`** は、C と C++ の両方のコンパイラで使用できます。

> [!NOTE]
> **`selectany`** 外部から参照できるグローバルデータ項目を実際に初期化する場合にのみ適用できます。

## <a name="example-selectany-attribute"></a>例: `selectany` 属性

このコードは、属性の使用方法を示してい **`selectany`** ます。

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

## <a name="example-use-selectany-attribute-to-ensure-data-comdat-folding"></a>例: `selectany` 属性を使用してデータ COMDAT を確実に圧縮する

このコードは、リンカーオプションを使用するときに、属性を使用してデータ COMDAT を確実に圧縮する方法を示して **`selectany`** [`/OPT:ICF`](../build/reference/opt-optimizations.md) います。 データは、でマーク **`selectany`** し、 **`const`** (readonly) セクションに配置する必要があることに注意してください。 読み取り専用セクションを明示的に指定する必要があります。

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

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`__declspec`](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
