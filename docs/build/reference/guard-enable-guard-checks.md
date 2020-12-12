---
description: 詳細情報:/ガード (ガードチェックを有効にする)
title: /GUARD (ガード チェックを有効にする)
ms.date: 11/04/2016
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
ms.openlocfilehash: 4f76de815bc10f8e1203510b25b237fe8db93444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191720"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (ガード チェックを有効にする)

実行可能イメージで、Control Flow Guard のチェックのサポートを指定します。

## <a name="syntax"></a>構文

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>解説

/GUARD:CF を指定した場合、リンカーは、Control Flow Guard (CFG) の実行時チェックをサポートしていることを示すように、.dll または .exe のヘッダーを変更します。 また、リンカーは、必要な制御フローのターゲット アドレス データをヘッダーに追加します。 既定では、/GUARD:CF は無効です。 /GUARD:NO を使用して明示的に無効化できます。 有効にするには、ガード: CF にも、既定でオンになっている [/DYNAMICBASE (アドレス空間レイアウトのランダム](dynamicbase-use-address-space-layout-randomization.md) 化を使用する) リンカーオプションが必要です。

[/Guard: cf](guard-enable-control-flow-guard.md)オプションを使用してソースコードをコンパイルすると、コンパイラは、可能なターゲットアドレスのすべての間接呼び出しを調べて制御フローを分析します。 コンパイラは、間接呼び出し命令のターゲット アドレスが、実行時に既知のターゲット アドレスの一覧にあることを検証するコードを挿入します。 CFG をサポートするオペレーティング システムは、CFG のランタイム チェックに失敗したプログラムを停止します。 これにより、データの破損を利用して呼び出し対象を変更することによって攻撃者が悪意のあるコードを実行することは、より難しくなります。

/GUARD:CF オプションは、CFG に対応する実行可能イメージを作成するために、コンパイラとリンカーの両方で指定する必要があります。 /GUARD:CF を使用してコンパイルされているもののリンクされていないコードでは、実行時チェックのコストが生じますが、CFG 保護を有効にしません。 1回の手順でコンパイルおよびリンクするコマンドに対して/GUARD: CF オプションを指定すると、 `cl` コンパイラはそのフラグをリンカーに渡します。 Visual Studio で **制御フローガード** プロパティが設定されている場合、/ガード: CF オプションはコンパイラとリンカーの両方に渡されます。 オブジェクトファイルまたはライブラリが個別にコンパイルされている場合は、コマンドでオプションを明示的に指定する必要があり `link` ます。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [ **構成プロパティ**]、[ **リンカー**]、[ **コマンドライン**] の順に展開します。

1. [ **追加オプション**] で、「」と入力し `/GUARD:CF` ます。

## <a name="see-also"></a>関連項目

[/guard (制御フロー ガードを有効にする)](guard-enable-control-flow-guard.md)<br/>
[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
