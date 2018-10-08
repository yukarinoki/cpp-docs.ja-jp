---
title: ATL プロジェクトで新しいインターフェイスの追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fec98fd785f5e99875c5f73b13ce1082c16add2b
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861760"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL プロジェクトで新しいインターフェイスの追加

オブジェクトまたはコントロールにインターフェイスを追加するときは、そのインターフェイスで各メソッドのスタブ関数を作成します。 オブジェクトまたはコントロールでは、既存のタイプ ライブラリ内にあるインターフェイスだけを追加できます。 また、インターフェイスを追加するクラスを実装する必要があります、 [BEGIN_COM_MAP](com-map-macros.md#begin_com_map)マクロ、または、プロジェクトに属性が場合があります、`coclass`属性。

2 つの方法のいずれかのコントロールに追加できる新しいインターフェイス: 手動でまたはクラス ビューでコード ウィザードを使用します。

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>クラス ビューでコード ウィザードを使用して、既存のオブジェクトまたはコントロールにインターフェイスを追加するには

1. [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)コントロールのクラス名を右クリックします。 たとえば、フル コントロールまたは複合コントロールは、またはそのヘッダー ファイルで、BEGIN_COM_MAP マクロを実装するその他のコントロール クラスにします。

1. ショートカット メニューで、**追加**、 をクリックし、**インターフェイスの実装**します。

1. 実装するインターフェイスを選択して、[インターフェイス実装ウィザード](../../ide/implement-interface-wizard.md)します。 インターフェイスが使用可能なタイプ ライブラリ内に存在しない場合する必要があります、手動で追加する .idl ファイルにします。

## <a name="to-add-a-new-interface-manually"></a>新しいインターフェイスを手動で追加するには

1. .Idl ファイルに新しいインターフェイスの定義を追加します。

1. オブジェクトやコントロールのインターフェイスから派生します。

1. 新規作成[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)インターフェイスの場合、プロジェクトに属性が追加、`coclass`属性。

1. インターフェイスのメソッドを実装します。

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ プロジェクトの種類](../../ide/visual-cpp-project-types.md)<br/>
[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)
