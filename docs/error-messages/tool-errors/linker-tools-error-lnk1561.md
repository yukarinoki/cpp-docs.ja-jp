---
title: リンカ ツール エラー LNK1561 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac24ed0c4aff4cbd7f0ea95ff71d0b8c4b3be09c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050763"
---
# <a name="linker-tools-error-lnk1561"></a>リンカ ツール エラー LNK1561

エントリ ポイントを定義する必要があります。

リンカーは検出されませんでした、*エントリ ポイント*、初期の関数で、実行可能ファイルを呼び出します。 既定では、リンカー検索、`main`または`wmain`コンソール アプリでは、関数、`WinMain`または`wWinMain`Windows アプリでは、関数または`DllMain`dll の初期化を必要とします。 別の関数を使用して指定することができます、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプション。

このエラーは、いくつかの原因を持つことができます。
- リンク ファイルの一覧のエントリ ポイントを定義するファイルが含まれていない可能性があります。 エントリ ポイント関数を含むファイルがアプリにリンクされていることを確認します。
- 間違った関数のシグネチャ; を使用して、エントリ ポイントを定義している可能性があります。たとえば、可能性がありますがスペルが間違っているまたは関数名では、正しくない場合に使用や戻り値の型やパラメーターの型を正しく指定します。
- 指定した可能性がありますいない、 [/DLL](../../build/reference/dll-build-a-dll.md) DLL のビルド時のオプションします。
- 場合がありますが正しく指定されていないエントリ ポイント関数の名前を使用した場合、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプション。
- 使用する場合、 [LIB](../../build/reference/lib-reference.md) DLL をビルドするツール、.def ファイルを指定する可能性があります。 そうである場合は、ビルドの .def ファイルを削除します。

アプリを構築するには、リンカーは、コードを開始するために呼び出すのエントリ ポイント関数が検索されます。 これは、アプリが読み込まれ、ランタイムを初期化後に呼び出される関数です。 アプリのエントリ ポイント関数を指定する必要があります。 またはアプリを実行できません。 エントリ ポイントでは、DLL の省略可能です。 既定では、いくつかの特定の名前とシグネチャのいずれかなどが含まれるエントリ ポイント関数の次のリンカー`int main(int, char**)`します。 別の関数名を指定するには、エントリとして、/ENTRY リンカー オプションを使用してポイント。

## <a name="example"></a>例

次の例では、LNK1561 が生成されます。

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```