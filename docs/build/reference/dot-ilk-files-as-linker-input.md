---
description: 詳細については、「」を参照してください。リンカー入力としての Ilk ファイル
title: リンカー入力としての .ilk ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 0aaa5fac19cedb8d94fc6dc9ab03a0f23fa0e49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192734"
---
# <a name="ilk-files-as-linker-input"></a>リンカー入力としての .ilk ファイル

インクリメンタルリンクを行うと、最初の増分リンクの間に作成した .ilk ステータスファイルが更新されます。 このファイルの基本名は .exe ファイルまたは .dll ファイルと同じで、拡張子は .ilk です。 後続のインクリメンタルリンクの間に、リンクによって .ilk ファイルが更新されます。 .Ilk ファイルが見つからない場合、LINK はフルリンクを実行し、新しい .ilk ファイルを作成します。 .Ilk ファイルが使用できない場合、リンクはインクリメンタルリンクを実行します。 インクリメンタルリンクの詳細については、「 [インクリメンタル (/INCREMENTAL)](incremental-link-incrementally.md) オプションのリンク」を参照してください。

## <a name="see-also"></a>関連項目

[リンク入力ファイル](link-input-files.md)<br/>
[MSVC リンカー オプション](linker-options.md)
