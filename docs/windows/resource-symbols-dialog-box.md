---
title: リソース シンボル ダイアログ ボックス (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourcesymbols
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 064fb9adce8b41c13709819f7ce0b7c515fea12a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313170"
---
# <a name="resource-symbols-dialog-box-c"></a>リソース シンボル ダイアログ ボックス (C++)

**リソース シンボル**C++ ダイアログ ボックスでは、新しいリソース シンボルの追加、シンボルが表示されます、またはシンボルが使用中は、ソース コード内の場所へのスキップを変更することができます。

**Name**  
シンボルの名前を表示します。 詳細については、次を参照してください。[シンボル名の制限](../windows/symbol-name-restrictions.md)します。

**[値]**  
シンボルの数値を表示します。 詳細については、次を参照してください。[シンボル値の制限](../windows/symbol-value-restrictions.md)します。

**使用中**  
シンボルが 1 つ以上のリソースで使用されることを指定する場合にオンにします。 リソースの一覧が [次のリソースで使用] ボックスに表示されます。

**読み取り専用のシンボルを表示します。**  
読み取り専用のリソースを表示する場合にオンにします。 既定で、**リソース シンボル** ダイアログ ボックスにリソース スクリプト ファイルで変更可能なリソースのみが表示されますが、このオプションを選択すると、変更可能なリソースは太字で表示されます。 および読み取り専用のリソースはプレーン テキストで表示されます。

**使用されます。**  
シンボル一覧で選択したシンボルを使用するリソースが表示されます。 特定のリソース エディターに移動するでリソースを選択します。、**使用者**ボックスと [] をクリック**ビュー使用**。 詳細については、次を参照してください。[特定のシンボル用のリソース エディターを開く](../windows/opening-the-resource-editor-for-a-given-symbol.md)します。

**新規**  
開く、**新しいシンボル** ダイアログ ボックスで、名前を定義することができ、必要に応じて、新しいシンボル リソース識別子の値。 詳細については、次を参照してください。[シンボルの新規作成](../windows/creating-new-symbols.md)です。

**変更**  
開く、**シンボルの変更** ダイアログ ボックスで、名前またはシンボルの値を変更することができます。 使用中のコントロールまたはリソースのシンボルを変更するには、対応するリソース エディターを使用する必要があります。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)します。

**ビューの使用**  
対応するリソース エディターで、シンボルが含まれたリソースを開きます。 詳細については、次を参照してください。[特定のシンボル用のリソース エディターを開く](../windows/opening-the-resource-editor-for-a-given-symbol.md)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース シンボルの表示](../windows/viewing-resource-symbols.md)