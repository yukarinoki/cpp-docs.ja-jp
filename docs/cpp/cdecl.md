---
title: __cdecl
ms.date: 10/09/2018
f1_keywords:
- __cdecl_cpp
- __cdecl
- _cdecl
- cdecl
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
ms.openlocfilehash: 298485d310ee4039b13781a8b5cd88a489af3b8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550216"
---
# <a name="cdecl"></a>__cdecl

**Microsoft 固有の仕様**

**_ _cdecl** C および C++ プログラムの呼び出し規約を既定値です。 実行できるため、スタックは呼び出し元によってクリーンアップ、`vararg`関数。 **_ _Cdecl**よりも大きな実行可能ファイルを作成する呼び出し規約[_ _stdcall](../cpp/stdcall.md)、各関数の呼び出しにスタック クリーンアップ コードを含める必要があるためです。 次の一覧は、この呼び出し規則の実装例を示しています。

|要素|実装|
|-------------|--------------------|
|引数を渡す順序|右から左。|
|スタック メンテナンスの役割|呼び出し元の関数によって、スタックから引数がポップされます。|
|名前装飾規約|アンダー スコア文字 (_) の場合を除き、名にプレフィックスが付いた\_C リンケージを使用する _cdecl 関数をエクスポートします。|
|大文字と小文字の変換規約|大文字小文字は変換されません。|

> [!NOTE]
>  関連情報については、[装飾名](../build/reference/decorated-names.md)を参照してください。

場所、 **_ _cdecl**変数または関数名の前に修飾子。 C の名前と呼び出し規則は、既定値であるためだけの時間使用する必要あります **_ _cdecl** x86 コードは、指定したときに、 `/Gv` (vectorcall)、 `/Gz` (stdcall)、または`/Gr`(fastcall)コンパイラ オプション。 [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションの強制、 **_ _cdecl**呼び出し規約。

ARM と x64 プロセッサでは、 **_ _cdecl**受け入れは通常、コンパイラによって無視されます。 ARM と x64 の規約に基づいて、引数は可能であればレジスタで渡され、残りの引数はスタックで渡されます。 X64 コードを使用して、 **_ _cdecl**を上書きする、 **/Gv**コンパイラ オプションと既定の x64 呼び出し規則を使用します。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。 次のクラス定義があるとします。

```cpp
struct CMyClass {
   void __cdecl mymethod();
};
```

ここで、

```cpp
void CMyClass::mymethod() { return; }
```

は次の記述と同じです。

```cpp
void __cdecl CMyClass::mymethod() { return; }
```

以前のバージョンとの互換性のため**cdecl**と **_cdecl**のシノニムは **_ _cdecl**しない限り、コンパイラ オプション[/Za\(を無効にします。言語拡張機能)](../build/reference/za-ze-disable-language-extensions.md)を指定します。

## <a name="example"></a>例

次の例では、コンパイラは、`system` 関数に対して C の命名規則と呼び出し規則を使用するように指示されます。

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>関連項目

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)<br/>
[キーワード](../cpp/keywords-cpp.md)