---
title: 順序 (関数の順序) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
dev_langs:
- C++
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de9b0fb629a1bf984929ec170f05e25e740e9cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378484"
---
# <a name="order-put-functions-in-order"></a>/ORDER (関数の順序)

(COMDAT) 関数を個別にパッケージのリンクの順序を指定します。

## <a name="syntax"></a>構文

>/注文: @*ファイル名*

### <a name="parameters"></a>パラメーター

*ファイル名*  
COMDAT 関数のリンクの順序を指定するテキスト ファイルです。

## <a name="remarks"></a>コメント

**/Order**コンパイラ オプションでは、関数が呼び出す関数と共に関数をグループ化して、プログラムのページングの動作を最適化することができます。 頻繁に呼び出される関数を一緒にグループすることもできます。 呼ばれるこれらの手法*スワップ調整*または*ページング最適化*、呼び出された関数が、メモリが必要な場合はディスクからポケットベル通知を送信する必要はありませんする可能性は向上します。

オブジェクト ファイルに、ソース コードをコンパイルするときと呼ばれる独自のセクションの各関数にコンパイラに通知することができます、 *COMDAT*を使用して、 [/Gy (関数レベルのリンクを有効にする)](../../build/reference/gy-enable-function-level-linking.md)コンパイラオプション。 **/Order**リンカー オプションを指定した順序で実行可能イメージに Comdat を配置するリンカーに指示します。

COMDAT の順序を指定するには、作成、*応答ファイル*、リンカーによって配置される順序で行ごとに 1 つには、名前で各 COMDAT を一覧表示するテキスト ファイルです。 このファイルの名前を渡す、*ファイル名*のパラメーター、 **/order**オプション。 C++ 関数の場合、COMDAT の名前は、関数名の装飾形式です。 C 関数の非装飾名を使用して`main`、として宣言されている C++ 関数と`extern "C"`です。 関数名および装飾名は大文字小文字を区別します。 装飾名の詳細については、次を参照してください。[装飾名](../../build/reference/decorated-names.md)です。 

使用して、Comdat の装飾名を検索する、 [DUMPBIN](../../build/reference/dumpbin-reference.md)ツールの[/symbols](../../build/reference/symbols.md)オブジェクト ファイルでオプションです。 リンカー先頭にアンダー スコアが自動的に追加 (\_) 関数への応答で名前ファイルの名前の先頭に疑問符 (?) またはアット マークしない限り、(@)。 たとえば、ソース ファイル、example.cpp、関数が含まれます`int cpp_func(int)`、`extern "C" int c_func(int)`と`int main(void)`のコマンドは、`DUMPBIN /SYMBOLS example.obj`これら装飾名を一覧表示。

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

この場合、名前を指定`?cpp_func@@YAHH@Z`、 `c_func`、および`main`応答ファイルにします。

1 つ以上の場合 **/order**リンカー オプション オプションが表示される、指定された最後の 1 つは有効になります。

**/Order**オプションは、インクリメンタル リンクを無効になります。 リンカー警告が表示される[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)インクリメンタル リンクが有効になっている場合、または指定した場合に、このオプションを指定すると、 [/ZI (増分 PDB)](../../build/reference/z7-zi-zi-debug-information-format.md)コンパイラ オプション。 この警告をミュートするには、使用することができます、 [/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)インクリメンタル リンクをオフにして、使用するリンカー オプション、 [/Zi (生成 PDB)](../../build/reference/z7-zi-zi-debug-information-format.md)インクリメンタル リンクせずに PDB を生成するコンパイラ オプション。

> [!NOTE]
> 静的関数名は、パブリック シンボル名ではないために、リンクで静的関数を注文することはできません。 ときに **/order**指定すると、リンカー警告[LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md)が静的であるか、見つかりませんである注文の応答ファイル内の各シンボルを生成します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  

1. **構成プロパティ**、開かれている**リンカー**を選択し、**最適化**プロパティ ページ。

1. 変更、**関数の順序**応答ファイルの名前を格納するプロパティです。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
[リンカー オプション](../../build/reference/linker-options.md)