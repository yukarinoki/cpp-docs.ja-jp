---
title: __fastcall
ms.date: 12/17/2018
f1_keywords:
- __fastcall_cpp
- __fastcall
- _fastcall
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
ms.openlocfilehash: 420552dd62c46ab5c2fa7e201387f258617f8453
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227479"
---
# <a name="__fastcall"></a>__fastcall

**Microsoft 固有の仕様**

**`__fastcall`** 呼び出し規則は、可能であれば、関数への引数をレジスタに渡すことを指定します。 この呼び出し規則は x86 アーキテクチャのみに適用されます。 次の一覧は、この呼び出し規約の実装例を示しています。

|要素|実装|
|-------------|--------------------|
|引数を渡す順序|左から右への引数リストで見つかる最初の 2 つの DWORD またはこれより小さい引数は、ECX および EDX レジスタに渡されます。他の引数はすべてスタック上で右から左へ渡されます。|
|スタック メンテナンスの役割|呼び出された関数によって、スタックから引数がポップされます。|
|名前装飾規約|アットマーク ( \@ ) は名前の前に付けられます。パラメーターリスト内のアットマーク (10 進数) の後には、名前がサフィックスとして付けられます。|
|大文字と小文字の変換規約|大文字小文字は変換されません。|

> [!NOTE]
> 将来のコンパイラ バージョンは、パラメーターを格納するために別のレジスタを使用する可能性があります。

[/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラオプションを使用すると、競合する属性を使用して **`__fastcall`** 関数が宣言されていない場合、または関数の名前がの場合を除き、モジュールの各関数がとしてコンパイルされ `main` ます。

キーワードは、 **`__fastcall`** ARM および x64 アーキテクチャを対象とするコンパイラによって受け入れられ、無視されます。 x64 チップでは、慣例により、最初の4つの引数は可能な限りレジスタに渡され、その他の引数はスタックで渡されます。 詳細については、「 [X64 呼び出し規則](../build/x64-calling-convention.md)」を参照してください。 ARM チップでは、最大で 4 個の整数引数と 8 個の浮動小数点引数をレジスタに渡すことができます。追加の引数はスタック上に渡されます。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規約の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。 次のクラス定義があるとします。

```cpp
struct CMyClass {
   void __fastcall mymethod();
};
```

ここで、

```cpp
void CMyClass::mymethod() { return; }
```

は次の記述と同じです。

```cpp
void __fastcall CMyClass::mymethod() { return; }
```

以前のバージョンとの互換性 **_fastcall**を維持するために、 **`__fastcall`** コンパイラオプションの [ [ \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、_fastcall はのシノニムになります。

## <a name="example"></a>例

次の例では、関数 `DeleteAggrWrapper` にレジスタで引数が渡されます。

```cpp
// Example of the __fastcall keyword
#define FASTCALL    __fastcall

void FASTCALL DeleteAggrWrapper(void* pWrapper);
// Example of the __ fastcall keyword on function pointer
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[引数の引き渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
