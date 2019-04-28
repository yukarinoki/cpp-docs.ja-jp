---
title: /MANIFESTINPUT (マニフェスト入力の指定)
ms.date: 11/04/2016
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: bf192664a7a2402b06621167d91dff67ce0741a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321359"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (マニフェスト入力の指定)

マニフェスト入力ファイルをイメージに埋め込まれたマニフェストに含めるように指定します。

## <a name="syntax"></a>構文

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
埋め込みマニフェストに含めるマニフェスト ファイル。

## <a name="remarks"></a>Remarks

**/MANIFESTINPUT**オプションを使用して実行可能イメージに埋め込みマニフェストを作成する入力ファイルのパスを指定します。 複数のマニフェスト入力ファイルがある場合は、スイッチを複数回使用します (入力ファイルごとに 1 回)。 マニフェスト入力ファイルは埋め込みマニフェストを作成するためにマージされます。 このオプションが必要です、 **/manifest: 埋め込む**オプション。

このオプションは、Visual Studio で直接設定することはできません。 代わりに、使用、**追加のマニフェスト ファイル**に含める追加のマニフェスト ファイルを指定するプロジェクトのプロパティ。 詳細については、次を参照してください。[入力と出力、マニフェスト ツール、構成プロパティ、\<プロジェクト名 > プロパティ ページ ダイアログ ボックス](input-and-output-manifest-tool.md)します。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
