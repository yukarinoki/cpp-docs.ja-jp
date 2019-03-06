---
title: ファイル名分割構文
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 159558081fd9884f969ddc66833d927b8569a79b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417477"
---
# <a name="filename-parts-syntax"></a>ファイル名分割構文

コマンド内のファイル名分割構文 (が暗黙の依存があります) 最初の依存ファイル名のコンポーネントを表します。 ファイル名のコンポーネントは、ディスク上に存在するではありませんが、ファイルのドライブ、パス、基本名、および拡張機能として、指定しました。 使用 **%s**を完全なファイル名を表します。 使用 **%&#124;**[*部分*]**F** (垂直バー文字に依存してパーセント記号) をファイル名の部分を表す場所*パーツ*任意の順序で、次の文字の 0 個以上にすることができます。

|文字|説明|
|------------|-----------------|
|文字がありません。|完全な名前 (同じ **%s**)|
|**d**|ドライブ|
|**p**|パス|
|**f**|ファイルのベース名|
|**e**|ファイル拡張子|

たとえば、ファイル名は c:\prog.exe とします。

- %s は c:\prog.exe になります

- %&#124;F c:\prog.exe になります

- %&#124;dF は c になります

- %&#124;pF は c:\ になります

- %&#124;fF prog になります

- %&#124;eF exe になります

## <a name="see-also"></a>関連項目

[メイクファイルのコマンド](../build/commands-in-a-makefile.md)
