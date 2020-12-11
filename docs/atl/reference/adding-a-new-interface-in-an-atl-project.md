---
description: 詳細については、ATL プロジェクトへの新しいインターフェイスの追加に関するページを参照してください。
title: ATL プロジェクトでの新しいインターフェイスの追加
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 7db5cd5f613985caf22253736ae691f3af9240ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159142"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL プロジェクトでの新しいインターフェイスの追加

オブジェクトまたはコントロールにインターフェイスを追加する場合は、そのインターフェイスのメソッドごとにスタブ関数を作成します。 オブジェクトまたはコントロールでは、既存のタイプライブラリに現在存在するインターフェイスのみを追加できます。 また、インターフェイスを追加するクラスは [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) マクロを実装する必要があります。また、プロジェクトに属性が設定されている場合は、属性を持つ必要があり `coclass` ます。

新しいインターフェイスをコントロールに追加するには、手動で行う方法とクラスビューのコードウィザードを使用する方法の2つの方法があります。

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>クラスビューのコードウィザードを使用して、既存のオブジェクトまたはコントロールにインターフェイスを追加するには

1. [クラスビュー](/visualstudio/ide/viewing-the-structure-of-code)で、コントロールのクラス名を右クリックします。 たとえば、フルコントロールまたは複合コントロール、またはヘッダーファイルに BEGIN_COM_MAP マクロを実装するその他のコントロールクラスなどです。

1. ショートカットメニューの [ **追加**] をクリックし、[ **インターフェイスの実装**] をクリックします。

1. [インターフェイスの実装ウィザード](../../ide/implementing-an-interface-visual-cpp.md#implement-interface-wizard)で実装するインターフェイスを選択します。 使用可能な typelib にインターフェイスが存在しない場合は、そのインターフェイスを .idl ファイルに手動で追加する必要があります。

## <a name="to-add-a-new-interface-manually"></a>新しいインターフェイスを手動で追加するには

1. 新しいインターフェイスの定義を .idl ファイルに追加します。

1. インターフェイスからオブジェクトまたはコントロールを派生させます。

1. インターフェイスの新しい [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) を作成するか、プロジェクトに属性が付けられている場合は属性を追加し `coclass` ます。

1. インターフェイスにメソッドを実装します。

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio の C++ プロジェクトの種類](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL および C Run-Time コードを使用したプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[既定の ATL プロジェクト構成](../../atl/reference/default-atl-project-configurations.md)
