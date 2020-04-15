---
title: リンカ ツール エラー LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: b397ef8e551f8cd6179392541e35183a5850454f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357747"
---
# <a name="linker-tools-error-lnk1561"></a>リンカ ツール エラー LNK1561

エントリ ポイントを定義する必要があります

リンカーは、実行可能ファイルで呼び出す最初の関数である*エントリ ポイント*を見つけませんでした。 既定では、リンカーは、コンソール`main`アプリ`wmain`、Windows アプリの`WinMain`または`wWinMain`関数、または`DllMain`初期化を必要とする DLL の関数を検索します。 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプションを使用して別の関数を指定できます。

このエラーには、次のようないくつかの原因があります。

- リンクするファイルの一覧に、エントリ ポイントを定義するファイルを含んでいない可能性があります。 エントリ ポイント関数を含むファイルがアプリにリンクされていることを確認します。
- 誤った関数シグネチャを使用してエントリ ポイントを定義した可能性があります。たとえば、関数名のスペルミスや大文字と小文字の間違い、戻り値の型またはパラメーター型の指定が間違っている場合などです。
- DLL のビルド時に[/DLL](../../build/reference/dll-build-a-dll.md)オプションを指定していない可能性があります。
- [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプションを使用したときに、エントリ ポイント関数の名前が正しく指定されていない可能性があります。
- [LIB](../../build/reference/lib-reference.md)ツールを使用して DLL をビルドしている場合は、.def ファイルを指定している可能性があります。 その場合は、ビルドから .def ファイルを削除します。

アプリをビルドするときに、リンカーはコードを開始するために呼び出すエントリ ポイント関数を探します。 これは、アプリが読み込まれ、ランタイムが初期化された後に呼び出される関数です。 アプリのエントリ ポイント関数を指定する必要があります。 DLL のエントリ ポイントは省略可能です。 既定では、リンカーは、 など`int main(int, char**)`、いくつかの特定の名前とシグネチャのいずれかを持つエントリ ポイント関数を検索します。 /ENTRY リンカー オプションを使用して、別の関数名をエントリ ポイントとして指定できます。

## <a name="example"></a>例

次のサンプルでは、LNK1561 が生成されます。

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
