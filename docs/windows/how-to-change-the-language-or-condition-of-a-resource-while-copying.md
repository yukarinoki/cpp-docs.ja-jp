---
title: '方法: (C++) のコピー中に、言語またはリソースの条件を変更する |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property [C++]
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3594e3c6ec839e41963ba7458e246563241bb4aa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066566"
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying-c"></a>方法: (C++) のコピー中に、言語またはリソースの条件を変更します。

リソースのコピー時に、リソースの言語プロパティ、条件プロパティ、またはその両方を変更できます。

- リソースの言語では、そのリソースで使用する言語のみを識別します。 これを使って[FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea)参照して、リソースを識別できるようにします。 (ただし、各言語でテキストに関連していない違いをリソースに含めることができます。たとえば、日本語キーボードのみで動作するアクセラレータや中国語でローカライズされたビルドのみに対応するビットマップなどです)。

- リソースの条件とは、リソースの特定のコピーが使用される条件を識別する定義済みのシンボルです。

リソースの言語と条件は、[ワークスペース] ウィンドウで、リソース名の後に、かっこで囲んで表示されます。 次の例では、リソース IDD_AboutBox が言語として Finnish、条件として XX33 を使用しています。

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>既存のリソースをコピーして、そのリソースの言語または条件を変更するには

1. .Rc ファイルまたは、[リソース ビュー](../windows/resource-view-window.md)ウィンドウで、コピーするリソースを右クリックします。

2. 選択**コピーの挿入**ショートカット メニューから。

3. **リソース コピーの挿入** ダイアログ ボックス。

   - **言語**ボックスの一覧で、言語を選択します。

   - **条件**ボックスに、条件を入力します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[方法: リソースをコピーする](../windows/how-to-copy-resources.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース エディター](../windows/resource-editors.md)