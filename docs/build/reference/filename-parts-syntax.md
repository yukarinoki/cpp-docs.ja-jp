---
description: 詳細については、「Filename-Parts 構文」を参照してください。
title: ファイル名分割構文
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 436481d52324b4c638b5fa0a9840ce0d9ef654f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192136"
---
# <a name="filename-parts-syntax"></a>ファイル名分割構文

コマンド内のファイル名-部分構文は、最初の依存ファイル名のコンポーネントを表します (暗黙的に依存している場合もあります)。 Filename コンポーネントは、ディスク上に存在するのではなく、指定されたファイルのドライブ、パス、基本名、および拡張子です。 完全なファイル名を表すには、 **% s** を使用します。 **% &#124;**[*parts*]**F** (パーセント記号の後に続く縦棒文字) を使用して、ファイル名の一部を表します。*部分* は、任意の順序で、次の文字の0個以上にすることができます。

|レター|説明|
|------------|-----------------|
|文字なし|完全な名前 ( **% s** と同じ)|
|**d**|ドライブ|
|**p**|パス|
|**f**|ファイルのベース名|
|**e**|[ファイル拡張子]|

たとえば、ファイル名が c:\prog.exe の場合は、次のようになります。

- % s は c:\prog.exe になります

- % &#124;F が c:\prog.exe されます

- % &#124;dF は c になります

- % &#124;pF は c:\ になります

- % &#124;fF は prog になります

- % &#124;eF は exe になります

## <a name="see-also"></a>関連項目

[メイクファイル内のコマンド](commands-in-a-makefile.md)
