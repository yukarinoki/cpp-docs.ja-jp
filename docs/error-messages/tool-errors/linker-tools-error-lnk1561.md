---
description: 詳細については、「リンカツール Error LNK1561」を参照してください。
title: リンカ ツール エラー LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: b8c99c6e4b016b1eee443cf8f166665f4f9ad894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310647"
---
# <a name="linker-tools-error-lnk1561"></a>リンカ ツール エラー LNK1561

エントリポイントを定義する必要があります

リンカーが、実行可能ファイルで呼び出す最初の関数である *エントリポイント* を見つけられませんでした。 既定では、リンカーは、コンソールアプリの場合は関数、Windows アプリの場合は関数、または `main` `wmain` `WinMain` `wWinMain` `DllMain` 初期化が必要な DLL を検索します。 [/Entry](../../build/reference/entry-entry-point-symbol.md)リンカーオプションを使用して、別の関数を指定できます。

このエラーには、いくつかの原因が考えられる場合があります。

- リンクするファイルの一覧にエントリポイントを定義するファイルが含まれていない可能性があります。 エントリポイント関数を含むファイルがアプリにリンクされていることを確認します。
- 間違った関数シグネチャを使用してエントリポイントを定義した可能性があります。たとえば、間違っているか、関数名に誤った大文字小文字が使用されているか、戻り値の型またはパラメーターの型が正しく指定されていない可能性があります。
- DLL をビルドするときに [/dll](../../build/reference/dll-build-a-dll.md) オプションを指定していない可能性があります。
- [/Entry](../../build/reference/entry-entry-point-symbol.md)リンカーオプションを使用したときに、エントリポイント関数の名前が正しく指定されていない可能性があります。
- [LIB](../../build/reference/lib-reference.md)ツールを使用して DLL をビルドする場合は、.def ファイルを指定している可能性があります。 その場合は、ビルドから .def ファイルを削除します。

アプリをビルドするときに、コードを開始するためにを呼び出すエントリポイント関数がリンカーによって検索されます。 これは、アプリが読み込まれ、ランタイムが初期化された後に呼び出される関数です。 アプリのエントリポイント関数を指定する必要があります。指定しないと、アプリを実行できません。 DLL のエントリポイントは省略可能です。 既定では、リンカーは、など、いくつかの特定の名前とシグネチャのいずれかを持つエントリポイント関数を検索し `int main(int, char**)` ます。 /ENTRY リンカーオプションを使用すると、エントリポイントとして別の関数名を指定できます。

## <a name="example"></a>例

次の例では、LNK1561 が生成されます。

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
