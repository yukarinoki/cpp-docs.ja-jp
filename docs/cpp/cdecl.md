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
ms.openlocfilehash: 9c1483d02bcb68d902cae527eb60e3ef9987607c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227583"
---
# <a name="__cdecl"></a>__cdecl

**`__cdecl`** は、C および C++ プログラムの既定の呼び出し規約です。 スタックは呼び出し元によってクリーンアップされるため、関数を実行でき `vararg` ます。 **`__cdecl`** 呼び出し規則により、 [__stdcall](../cpp/stdcall.md)よりも大きな実行可能ファイルが作成されます。これは、各関数呼び出しにスタッククリーンアップコードを含める必要があるためです。 次の一覧は、この呼び出し規約の実装例を示しています。 **`__cdecl`** 修飾子は Microsoft 固有です。

|要素|実装|
|-------------|--------------------|
|引数を渡す順序|右から左。|
|スタック メンテナンスの役割|呼び出し元の関数によって、スタックから引数がポップされます。|
|名前装飾規約|\_C リンケージを使用する _cdecl 関数がエクスポートされる場合を除き、アンダースコア文字 (_) は名前の前に付加されます。|
|大文字と小文字の変換規約|大文字小文字は変換されません。|

> [!NOTE]
> 関連情報については、「[装飾名](../build/reference/decorated-names.md)」を参照してください。

**`__cdecl`** 変数または関数名の前に修飾子を配置します。 C の名前と呼び出し規約は既定であるため、x86 コードでを使用する必要があるの **`__cdecl`** は、 `/Gv` (vectorcall)、 `/Gz` (stdcall)、または `/Gr` (fastcall) コンパイラオプションを指定した場合のみです。 [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラオプションは、呼び出し規約を強制的に実行し **`__cdecl`** ます。

ARM および x64 プロセッサで **`__cdecl`** は、は受け入れられますが、通常はコンパイラによって無視されます。 ARM と x64 の規約に基づいて、引数は可能であればレジスタで渡され、残りの引数はスタックで渡されます。 X64 コードでは、を使用して **`__cdecl`** **/Gv**コンパイラオプションをオーバーライドし、既定の x64 呼び出し規約を使用します。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規約の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。 次のクラス定義があるとします。

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

以前のバージョンとの互換性を維持 **_cdecl**するために、 **cdecl** **`__cdecl`** コンパイラオプション[/za \( Disable language extension)](../build/reference/za-ze-disable-language-extensions.md)が指定されていない限り、cdecl と _cdecl はのシノニムになります。

## <a name="example"></a>例

次の例では、コンパイラは、`system` 関数に対して C の命名規則と呼び出し規則を使用するように指示されます。

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>関連項目

[引数の引き渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
