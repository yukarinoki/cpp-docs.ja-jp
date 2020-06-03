---
title: /await (コルーチン サポートを有効にする)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: eeab3f4a1afc73e341f04222a55c8ce429490742
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078449"
---
# <a name="await-enable-coroutine-support"></a>/await (コルーチン サポートを有効にする)

コルーチンのコンパイラサポートを有効にするには、 **/await**コンパイラオプションを使用します。

## <a name="syntax"></a>構文

> /await

## <a name="remarks"></a>解説

**/Await**コンパイラオプションを使用すると、 C++コルーチンおよびキーワード**co_await**、 **co_yield**、および**co_return**のコンパイラサポートが有効になります。 このオプションは、既定ではオフになっています。 Visual Studio でのコルーチンのサポートについては、 [Visual Studio チームのブログ](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)を参照してください。 コルーチン standard 提案の詳細については、「 [N4628 Working Draft」、「 C++ Technical Specification For Extensions for コルーチン](https://wg21.link/n4628)」を参照してください。

**/Await**オプションは、Visual Studio 2015 以降で使用できます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティページ]** ダイアログボックスを開きます。

1. **[構成プロパティ]** で、 **[CC++ /]** フォルダー を展開し、 **[コマンドライン]** プロパティページをクリックします。

1. **[追加のオプション]** ボックスに、" **/await** " コンパイラオプションを入力します。 **[OK]** または **[適用]** を選択して、変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
