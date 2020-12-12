---
description: 詳細については、Command-Line Warning D9041 を参照してください。
title: コマンド ラインの警告 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: d6226d4e5dd89176c0ed3722a9fd24e1244cacac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119763"
---
# <a name="command-line-warning-d9041"></a>コマンド ラインの警告 D9041

> '/*option-name*' の値 '*option-value*' が無効です。'*仮定値 ' と* 想定します。この警告を指定するときに、コマンドラインオプションに '/analyze ' を追加します

**`/wd`** **`/we`** **`/wo`** **`/wl`** コマンドラインオプションを指定せずに、、、、またはコマンドラインオプションにコード分析の警告番号が追加されました **`/analyze`** 。 このエラーを解決するには、 **`/analyze`** コマンドラインオプションを追加するか、適切なコマンドラインオプションから無効な警告番号を削除し **`/w`** ます。

## <a name="example"></a>例

次のコマンドラインの例では、警告 D9041 が生成されます。

```cmd
cl /EHsc /LD /wd6001 filename.cpp
```

この警告を修正するには、 **`/analyze`** コマンドラインオプションを追加します。 **`/analyze`** ご使用のバージョンのコンパイラでがサポートされていない場合は、オプションから無効な警告番号を削除して **`/wd`** ください。

## <a name="see-also"></a>関連項目

[コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC コンパイラ オプション](../../build/reference/compiler-options.md)
