---
title: コマンド ラインの警告 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 7c685a1ca3195ad4ab52bab8b5d32b1a51534b24
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196576"
---
# <a name="command-line-warning-d9041"></a>コマンド ラインの警告 D9041

'/option ' の値 ' value ' が無効です。' value ' を想定しています。この警告を指定するときに、コマンドラインオプションに '/analyze ' を追加します

**/Analyze**コマンドラインオプションを指定せずに、 **/wd**、 **/we**、 **/wo**、または **/wl**コマンドラインオプションにコード分析の警告番号が追加されました。 このエラーを解決するには、 **/analyze**コマンドラインオプションを追加するか、適切な **/w**コマンドラインオプションから無効な警告番号を削除します。

## <a name="example"></a>例

次のコマンドラインの例では、警告 D9041 が生成されます。

```
cl /EHsc /LD /wd6001 filename.cpp
```

警告を修正するには、 **/analyze**コマンドラインオプションを追加します。 ご使用のバージョンのコンパイラで **/analyze**がサポートされていない場合は、 **/wd**オプションから無効な警告番号を削除してください。

## <a name="see-also"></a>参照

[コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC コンパイラ オプション](../../build/reference/compiler-options.md)
