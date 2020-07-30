---
title: __stdcall
ms.date: 10/10/2018
f1_keywords:
- __stdcall_cpp
- __stdcall
- _stdcall
helpviewer_keywords:
- __stdcall keyword [C++]
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
ms.openlocfilehash: 85d1b29fddece741aa94364bb6edfdf3b973faaf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213178"
---
# <a name="__stdcall"></a>__stdcall

**`__stdcall`** 呼び出し規約は、Win32 API 関数を呼び出すために使用されます。 呼び出し先がスタックを消去するので、コンパイラは関数を作成し `vararg` **`__cdecl`** ます。 この呼び出し規則を使用する関数には、関数プロトタイプが必要です。 **`__stdcall`** 修飾子は Microsoft 固有です。

## <a name="syntax"></a>構文

> *戻り値の型* **`__stdcall`***関数名*[ **`(`** *引数リスト* **`)`** ]

## <a name="remarks"></a>解説

次の一覧は、この呼び出し規約の実装例を示しています。

|要素|実装|
|-------------|--------------------|
|引数を渡す順序|右から左。|
|引数渡し規約|ポインターまたは参照型が渡されない場合は、値渡し。|
|スタック メンテナンスの役割|呼び出された関数が、自分の引数をスタックからポップします。|
|名前装飾規約|`_`名前の先頭にアンダースコア () が付きます。 名前の後にアットマーク () が続き、その `@` 後に引数リストのバイト数 (10 進数) が続きます。 したがって、`int func( int a, double b )` として宣言された関数は次のように修飾されます: `_func@12`|
|大文字と小文字の変換規約|なし|

[/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラオプションは、 **`__stdcall`** 別の呼び出し規約で明示的に宣言されていないすべての関数に対してを指定します。

以前のバージョンとの互換性のために、 **`_stdcall`** **`__stdcall`** コンパイラオプションの [ [ `/Za` \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、はのシノニムになります。

修飾子を使用して宣言された関数 **`__stdcall`** は、を使用して宣言された関数と同じ方法で戻り [`__cdecl`](../cpp/cdecl.md) ます。

ARM および x64 プロセッサで **`__stdcall`** は、はコンパイラによって受け入れられ、無視されます。 arm および x64 アーキテクチャでは、可能な場合は引数がレジスタに渡され、その後の引数はスタックで渡されます。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規約の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。 次のクラス定義の場合、

```cpp
struct CMyClass {
   void __stdcall mymethod();
};
```

this

```cpp
void CMyClass::mymethod() { return; }
```

は次の記述と同じです。

```cpp
void __stdcall CMyClass::mymethod() { return; }
```

## <a name="example"></a>例

次の例では、 **`__stdcall`** `WINAPI` 標準呼び出しとして処理されるすべての関数型の結果を使用しています。

```cpp
// Example of the __stdcall keyword
#define WINAPI __stdcall
// Example of the __stdcall keyword on function pointer
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>関連項目

[引数の引き渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
