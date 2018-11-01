---
title: /GUARD (ガード チェックを有効にする)
ms.date: 11/04/2016
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
ms.openlocfilehash: 730e26477f4684ca6339a25a945ae04ff5a823c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565907"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (ガード チェックを有効にする)

実行可能イメージで、Control Flow Guard のチェックのサポートを指定します。

## <a name="syntax"></a>構文

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>Remarks

/GUARD:CF を指定した場合、リンカーは、Control Flow Guard (CFG) の実行時チェックをサポートしていることを示すように、.dll または .exe のヘッダーを変更します。 また、リンカーは、必要な制御フローのターゲット アドレス データをヘッダーに追加します。 既定では、/GUARD:CF は無効です。 /GUARD:NO を使用して明示的に無効化できます。 /GUARD:CF を有効にする必要も、 [/DYNAMICBASE (使用してアドレス空間レイアウトのランダム化)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)リンカー オプションは、既定でオンになっています。

使用してソース コードをコンパイルするときに、 [/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)可能なターゲット アドレスのすべての間接的な呼び出しを調べることによってオプション、コンパイラの分析、制御フロー。 コンパイラは、間接呼び出し命令のターゲット アドレスが、実行時に既知のターゲット アドレスの一覧にあることを検証するコードを挿入します。 CFG をサポートするオペレーティング システムは、CFG のランタイム チェックに失敗したプログラムを停止します。 これにより、データの破損を利用して呼び出し対象を変更することによって攻撃者が悪意のあるコードを実行することは、より難しくなります。

/GUARD:CF オプションは、CFG に対応する実行可能イメージを作成するために、コンパイラとリンカーの両方で指定する必要があります。 /GUARD:CF を使用してコンパイルされているもののリンクされていないコードでは、実行時チェックのコストが生じますが、CFG 保護を有効にしません。 /GUARD:CF オプションが指定されている場合、`cl`コマンドを 1 つの手順では、コンパイラのコンパイルし、リンクは、フラグをリンカーに渡します。 ときに、**制御フロー ガード**プロパティは、Visual Studio の設定は、/GUARD:CF オプションは、コンパイラとリンカーの両方に渡されます。 オプションはで明示的に指定する必要がありますオブジェクト ファイルまたはライブラリは、個別にコンパイルされている、ときに、`link`コマンド。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 展開**構成プロパティ**、**リンカー**、**コマンドライン**します。

1. **追加オプション**、入力`/GUARD:CF`します。

## <a name="see-also"></a>関連項目

[/guard (制御フロー ガードを有効にする)](../../build/reference/guard-enable-control-flow-guard.md)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)