---
title: /MANIFESTINPUT (マニフェスト入力の指定)
ms.date: 07/24/2019
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: d7c8351c915f5666ada9939df686c81c86ab89ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337507"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (マニフェスト入力の指定)

マニフェスト入力ファイルをイメージに埋め込まれたマニフェストに含めるように指定します。

## <a name="syntax"></a>構文

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>パラメーター

*Filename*<br/>
埋め込みマニフェストに含めるマニフェスト ファイル。

## <a name="remarks"></a>解説

**/MANIFESTINPUT**オプションは、実行可能なイメージに埋め込みマニフェストを作成するために使用する入力ファイルのパスを指定します。 複数のマニフェスト入力ファイルがある場合は、スイッチを複数回使用します (入力ファイルごとに 1 回)。 マニフェスト入力ファイルは埋め込みマニフェストを作成するためにマージされます。 このオプションには **、/マニフェスト:EMBED**オプションが必要です。

このオプションは、Visual Studio で直接設定することはできません。 代わりに、プロジェクトの**追加マニフェスト ファイル**プロパティを使用して、追加のマニフェスト ファイルを指定します。 詳細については、「[マニフェスト ツールのプロパティ ページ](manifest-tool-property-pages.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
