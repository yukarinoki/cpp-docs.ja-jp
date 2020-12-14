---
description: 「/ORDER (関数の順序)」を参照してください。
title: /ORDER (関数の順序)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
ms.openlocfilehash: 36888cbb24c869d06eaaa5830b95ae76fc42b860
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226351"
---
# <a name="order-put-functions-in-order"></a>/ORDER (関数の順序)

個別にパッケージ化された (COMDAT) 関数のリンク順序を指定します。

## <a name="syntax"></a>構文

> **/Order: \@**<em>ファイル名</em>

### <a name="parameters"></a>パラメーター

*filename*<br/>
COMDAT 関数のリンク順序を指定するテキストファイルです。

## <a name="remarks"></a>解説

**/Order** コンパイラオプションを使用すると、関数を呼び出した関数と共にグループ化することで、プログラムのページング動作を最適化できます。 頻繁に呼び出される関数をまとめてグループ化することもできます。 *スワップのチューニング* または *ページングの最適化* と呼ばれるこれらの手法によって、呼び出された関数が必要なときにメモリに存在し、ディスクからページングされる必要がないという確率が高くなります。

ソースコードをオブジェクトファイルにコンパイルする場合は、 [/gy (関数レベルのリンクの有効化)](gy-enable-function-level-linking.md)コンパイラオプションを使用して、各関数を *COMDAT* と呼ばれる独自のセクションに配置するようにコンパイラに指示できます。 **/Order** リンカーオプションは、指定した順序で、実行可能イメージに comdat を配置するようにリンカーを設定します。

COMDAT の順序を指定するには、 *応答ファイル* を作成します。これは、各 COMDAT を1行に1つずつ、リンカーによって配置される順序で一覧表示するテキストファイルです。 このファイルの名前を **/order** オプションの *filename* パラメーターとして渡します。 C++ 関数の場合、COMDAT の名前は、関数名の修飾された形式です。 `main`として宣言された C++ 関数には、非装飾名を C 関数、、およびに使用し `extern "C"` ます。 関数名と装飾名は大文字と小文字が区別されます。 装飾名の詳細については、「 [装飾名](decorated-names.md)」を参照してください。

Comdat の装飾名を検索するには、オブジェクトファイルの [DUMPBIN](dumpbin-reference.md) ツールの [/SYMBOLS](symbols.md) オプションを使用します。 リンカーは、 **\_** 名前が疑問符 (**?**) またはアットマーク () で始まっていない限り、応答ファイルの関数名にアンダースコア () を自動的に付加し **\@** ます。 たとえば、ソースファイル (.cpp など) に関数とが含まれている場合、 `int cpp_func(int)` `extern "C" int c_func(int)` `int main(void)` コマンドは `DUMPBIN /SYMBOLS example.obj` 次のような装飾名を一覧表示します。

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

この場合は、応答ファイルで、、およびという名前を指定し `?cpp_func@@YAHH@Z` `c_func` `main` ます。

リンカーオプションに複数の **/order** オプションが表示されている場合は、最後に指定したものが有効になります。

**/Order** オプションは、インクリメンタルリンクを無効にします。 インクリメンタルリンクが有効になっている場合、または[/zi (インクリメンタル PDB)](z7-zi-zi-debug-information-format.md)コンパイラオプションを指定した場合は、このオプションを指定すると、リンカーの警告[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)が表示されることがあります。 この警告が表示されないようにするには、 [/INCREMENTAL: NO](incremental-link-incrementally.md) リンカーオプションを使用してインクリメンタルリンクを無効にし、 [/zi (pdb の生成)](z7-zi-zi-debug-information-format.md) コンパイラオプションを使用してインクリメンタルリンクを行わずに pdb を生成します。

> [!NOTE]
> 静的関数名がパブリックシンボル名ではないため、リンクで静的関数を順序付けることはできません。 **/Order** が指定されている場合、LNK4037 は、順序応答ファイル内の各シンボルに対して、静的な、または見つからなかったリンカー警告 [](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md)が生成されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー** の  >  **最適化**] プロパティページを選択します。

1. 応答ファイルの名前を含むように、 **関数の順序** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
