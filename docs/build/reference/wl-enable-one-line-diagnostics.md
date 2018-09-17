---
title: -WL (1 行診断の有効化) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /wl
dev_langs:
- C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e82a3273673d45d1abf3ac201d7a0f63334cecbb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718673"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (1 行診断の有効化)

エラーまたは警告メッセージには、追加情報を追加します。

## <a name="syntax"></a>構文

```
/WL
```

## <a name="remarks"></a>Remarks

エラーと C++ コンパイラの警告メッセージは、追加情報が表示されたら、既定では、新しい行を実行できます。 コマンドラインからコンパイルするときに、エラーまたは警告メッセージに追加情報の行を追加できます。 ログ ファイルに、ビルドの出力をキャプチャして、すべてのエラーと警告を検索するには、そのログを処理する場合、望ましく場合があります。 セミコロンは、追加の行からエラーまたは警告メッセージを分離は。

すべてのエラーと警告メッセージがある追加情報の行。 次のコードでは、情報の追加行があるエラーを生成します。使用する場合の効果をテストすることは **/WL**します。

```
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)