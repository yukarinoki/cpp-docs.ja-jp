---
title: /HIGHENTROPYVA (64 ビット ASLR のサポート)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 8f8601d89e8456461aac3d91f9fd2cfda216d7f5
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373841"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 ビット ASLR のサポート)

実行可能ファイル イメージが高いエントロピの 64 ビット ASLR (Address Space Layout Randomization) をサポートするかどうかを指定します。

## <a name="syntax"></a>Syntax

> **/HIGHENTROPYVA**[**: NO**]

## <a name="remarks"></a>解説

**/HIGHENTROPYVA**は、ASLR が64ビットのアドレス空間全体を使用できるかどうかを示すために、.dll ファイルまたは .exe ファイルの*実行可能イメージ*のヘッダーを変更します。 このオプションを実行可能ファイルおよび依存するモジュールのすべてに設定すると、64 ビット ASLR をサポートするオペレーティング システムは、読み込み時に 64 ビットの仮想アドレス空間でランダム化されたアドレスを使用して、実行可能イメージのセグメントのベース アドレスをリベースできます。 この大きいアドレス空間により、攻撃者は特定のメモリ領域の位置を推測することが困難となります。

既定では、64ビットの実行可能イメージに対して **/HIGHENTROPYVA**が有効になっています。 このオプションには[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)が必要です。これは64ビットイメージでも既定で有効になっています。 **/HIGHENTROPYVA**は、32ビットの実行可能イメージには適用されません。リンカーはこのオプションを無視します。 このオプションを明示的に無効にするには、 **/HIGHENTROPYVA: NO**を使用します。

読み込み時に **/HIGHENTROPYVA**が効果を持つようにするには、 [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)も有効にする必要があります。 **/DYNAMICBASE**は既定で有効になっており、Windows Vista 以降のオペレーティングシステムで ASLR を有効にするために必要です。 以前のバージョンの Windows では、このフラグは無視します。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] で、またはを入力し `/HIGHENTROPYVA` `/HIGHENTROPYVA:NO` ます。

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Windows ISV ソフトウェアセキュリティ防御](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
