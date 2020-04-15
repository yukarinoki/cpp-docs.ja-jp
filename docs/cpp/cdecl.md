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
ms.openlocfilehash: b4a86c49880b0c40d402c7cec863f79e24bc4dc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371563"
---
# <a name="__cdecl"></a>__cdecl

**__cdecl**は、C および C++ プログラムの既定の呼び出し規約です。 スタックは呼び出し元によってクリーンアップされるため、機能を`vararg`実行できます。 **__cdecl**呼び出し規約では、各関数呼び出しにスタック クリーンアップ コードを含める必要があるため[、__stdcall](../cpp/stdcall.md)よりも大きな実行可能ファイルが作成されます。 次の一覧は、この呼び出し規約の実装例を示しています。 **__cdecl**修飾子は、マイクロソフト固有です。

|要素|実装|
|-------------|--------------------|
|引数を渡す順序|右から左。|
|スタック メンテナンスの役割|呼び出し元の関数によって、スタックから引数がポップされます。|
|名前装飾規約|C リンケージを使用する_cdecl関数がエクスポートされる場合\_を除き、アンダースコア文字 (_) は名前に接頭辞が付けられます。|
|大文字と小文字の変換規約|大文字小文字は変換されません。|

> [!NOTE]
> 関連情報については、「[装飾名](../build/reference/decorated-names.md)」を参照してください。

変数または関数名の前に **__cdecl**修飾子を置きます。 C の命名規則と呼び出し規約がデフォルトであるため、x86 コードで **__cdecl**使用する必要があるのは`/Gv`、(ベクトルコール)、(stdcall)、`/Gz`または`/Gr`(fastcall) コンパイラー・オプションを指定した場合だけです。 [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションは **、__cdecl**呼び出し規約を強制します。

ARM および x64 プロセッサでは **、__cdecl**は受け入れられますが、通常はコンパイラによって無視されます。 ARM と x64 の規約に基づいて、引数は可能であればレジスタで渡され、残りの引数はスタックで渡されます。 x64 コードでは **、__cdecl**を使用して **/Gv**コンパイラ オプションをオーバーライドし、既定の x64 呼び出し規約を使用します。

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

以前のバージョンとの互換性のために **、cdecl**と **_cdecl**は、コンパイラ オプション[/Za\(無効化言語拡張機能) が](../build/reference/za-ze-disable-language-extensions.md)指定されていない限り **、__cdecl**の同義語です。

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
[Keywords](../cpp/keywords-cpp.md)
