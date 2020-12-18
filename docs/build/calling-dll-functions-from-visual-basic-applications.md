---
description: '詳細情報: DLL 関数の Visual Basic アプリケーションからの呼び出し方'
title: DLL 関数の Visual Basic アプリケーションからの呼び出し方
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
ms.openlocfilehash: 3c9a66a4d6dc9a8e3cc6e8b8a80584d430f12562
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156984"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>DLL 関数の Visual Basic アプリケーションからの呼び出し方

Visual Basic アプリケーション (や Pascal、Fortran などの他の言語で書かれたアプリケーション) から C/C++ DLL 内の関数を呼び出すには、正しい呼び出し規則を使い、コンパイラによって名前装飾されずに、エクスポートされる必要があります。

**`__stdcall`** は、関数の正しい呼び出し規則を作成します。つまり、呼び出された関数がスタックをクリアし、パラメーターは右から左へ渡されます。ただし、関数名は異なる方法で装飾されます。 このため、 **`__declspec(dllexport)`** が DLL 内のエクスポート関数で使用される場合は、装飾名がエクスポートされます。

**`__stdcall`** で装飾された名前には、シンボル名の前にアンダースコア ( **\_** ) が付けられ、シンボルの後にはアット マーク ( **\@** ) が付けられ、その後に引数リストのバイト数 (必要なスタック空間) が付けられます。 結果として、宣言時の関数は次のようになります。

```C
int __stdcall func (int a, double b)
```

は、出力の `_func@12` として修飾されます。

C の呼び出し規則 ( **`__cdecl`** ) による装飾では、名前は `_func` となります。

装飾名を取得するには、[/MAP](reference/map-generate-mapfile.md) を使用します。 **`__declspec(dllexport)`** を使用すると、次の処理が行われます。

- 関数が C の呼び出し規則 ( **`__cdecl`** ) を使用してエクスポートされる場合、先頭のアンダースコア ( **\_** ) は名前のエクスポート時に除去されます。

- エクスポートされる関数が C の呼び出し規則を使わない場合 ( **`__stdcall`** など) は、装飾名がエクスポートされます。

スタックがクリアされた場所をオーバーライドする方法はないので、 **`__stdcall`** を使う必要があります。 **`__stdcall`** を使って装飾を外すには、.def ファイルの EXPORTS セクションのエイリアスを使って、その名前を指定する必要があります。 関数宣言の例を次に示します。

```C
int  __stdcall MyFunc (int a, double b);
void __stdcall InitCode (void);
```

.DEF ファイルの内容は、次のとおりです。

```
EXPORTS
   MYFUNC=_MyFunc@12
   INITCODE=_InitCode@0
```

Visual Basic で書かれたプログラムから DLL を呼び出す場合は、ここで示したエイリアスの手法を .def ファイル内で使用する必要があります。 エイリアスが Visual Basic プログラムの中で宣言されている場合は、.def ファイル内でのエイリアスは不要です。 これは、Visual Basic プログラムでは、[Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) ステートメントにエイリアス句を追加することで実現されます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [DLL からのエクスポート](exporting-from-a-dll.md)

- [.DEF ファイルを使った DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使った DLL からのエクスポート](exporting-from-a-dll-using-declspec-dllexport.md)

- [C 言語の実行形式で使う C++ 関数のエクスポート](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [装飾名](reference/decorated-names.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
