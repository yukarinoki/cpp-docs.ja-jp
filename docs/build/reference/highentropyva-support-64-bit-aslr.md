---
title: /HIGHENTROPYVA (64 ビット ASLR のサポート)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 929d6aa71010c1f303bf7a1ce64109a01b8792e4
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404126"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 ビット ASLR のサポート)

実行可能ファイル イメージが高いエントロピの 64 ビット ASLR (Address Space Layout Randomization) をサポートするかどうかを指定します。

## <a name="syntax"></a>構文

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>解説

**`/HIGHENTROPYVA`***実行可能イメージ*ファイル (たとえば、またはファイル) のヘッダーを変更して *`.dll`* *`.exe`* 、ASLR が64ビットのアドレス空間全体を使用できるかどうかを示します。  効果を与えるには、実行可能ファイルと、それが依存するすべてのモジュールに対してオプションを設定します。 その後、64ビット ASLR をサポートするオペレーティングシステムでは、64ビットのランダム化された仮想アドレスを使用して、読み込み時に実行可能イメージのセグメントをリベースできます。 この大きいアドレス空間により、攻撃者は特定のメモリ領域の位置を推測することが困難となります。

既定で **`/HIGHENTROPYVA`** は、64ビットの実行可能イメージに対してが有効になっています。 このオプションにはが必要です [`/LARGEADDRESSAWARE`](largeaddressaware-handle-large-addresses.md) 。これは、64ビットイメージでも既定で有効になっています。 **`/HIGHENTROPYVA`** 32ビットの実行可能イメージには適用されません。リンカーはこのオプションを無視します。 このオプションを明示的に無効にするには、を使用し **`/HIGHENTROPYVA:NO`** ます。

が **`/HIGHENTROPYVA`** 読み込み時に影響を与える場合は、 [`/DYNAMICBASE`](dynamicbase-use-address-space-layout-randomization.md) も有効にする必要があります。 **`/DYNAMICBASE`** は、既定で有効になっており、Windows Vista 以降のオペレーティングシステムで ASLR を有効にするために必要です。 以前のバージョンの Windows では、このフラグは無視します。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] で、またはを入力し `/HIGHENTROPYVA` `/HIGHENTROPYVA:NO` ます。

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
- [`/DYNAMICBASE`](dynamicbase-use-address-space-layout-randomization.md)
- [`/LARGEADDRESSAWARE`](largeaddressaware-handle-large-addresses.md)
- [Windows ISV ソフトウェアセキュリティ防御](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
