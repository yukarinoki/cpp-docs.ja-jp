---
description: 詳細については、「COM + 1.0」、「ATL COM + 1.0 コンポーネントウィザード」を参照してください。
title: COM+ 1.0、ATL COM+ 1.0 コンポーネント ウィザード
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: 581a258fc2702465fea40590430080bb6b9fcd66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141298"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0、ATL COM+ 1.0 コンポーネント ウィザード

::: moniker range="msvc-160"

このウィザードは Visual Studio 2019 以降で使用できません。

::: moniker-end

::: moniker range="<=msvc-150"

ATL COM+ 1.0 コンポーネント ウィザードのこのページを使用して、サポートするインターフェイスの種類と追加のインターフェイスを指定します。

ATL プロジェクトや ATL COM クラスの詳細については、「[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)」を参照してください。

- **Interface**

   オブジェクトでサポートされるインターフェイスの種類を示します。 既定で、オブジェクトではデュアル インターフェイスがサポートされます。

   |オプション|説明|
   |------------|-----------------|
   |**デュアル**|オブジェクトでデュアル インターフェイス (その vtable にカスタム インターフェイス関数と遅延バインディング `IDispatch` メソッドがある) をサポートするように指定します。 COM クライアントとオートメーション コントローラーの両方に、オブジェクトへのアクセスを許可します。|
   |**Custom**|オブジェクトでカスタム インターフェイス (その vtable にカスタム インターフェイス関数がある) をサポートするように指定します。 カスタム インターフェイスは、特にプロセスの境界間で、デュアル インターフェイスよりも速い可能性があります。<br /><br /> - **オートメーション互換** カスタム インターフェイスにオートメーションのサポートを追加します。 属性付きプロジェクトの場合は、コクラスに **oleautomation** 属性を設定します。|

- **Queueable**

   クライアントがメッセージ キューを使用して、非同期的にこのコンポーネントを呼び出すことができることを示します。 .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) に、コンポーネント属性付きマクロ custom(TLBATTR_QUEUEABLE, 0) を追加します。

- **サポート**

   エラー処理とオブジェクト コントロールの追加サポートを示します。

   |オプション|説明|
   |------------|-----------------|
   |**ISupportErrorInfo**|オブジェクトがクライアントにエラー情報を返すことができるように、[ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) インターフェイスのサポートを作成します。|
   |**IObjectControl**|オブジェクトに、[アクティブ化](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-activate)、 [canbepooled](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled)、および[非アクティブ化](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate)の3つの[IObjectControl](/windows/win32/api/comsvcs/nn-comsvcs-iobjectcontrol)メソッドへのアクセスを提供します。|
   |**IObjectConstruct**|他のメソッドやオブジェクトからのパラメーターの受け渡しを管理するための [IObjectConstruct](/windows/win32/api/comsvcs/nn-comsvcs-iobjectconstruct) インターフェイスのサポートを作成します。|

- **トランザクション**

   オブジェクトがトランザクションをサポートすることを示します。 .idl ファイル (属性なしプロジェクト) に mtxattr.h ファイルを含めます。

   |オプション|説明|
   |------------|-----------------|
   |**サポートされています**|コンポーネント属性マクロ custom(TLBATTR_TRANS_SUPPORTED,0) を .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) に追加して、オブジェクトがトランザクション ストリームのルートにならないことを指定します。|
   |**必須**|コンポーネント属性マクロ custom(TLBATTR_TRANS_REQUIRED,0) を .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) に追加して、オブジェクトがトランザクション ストリームのルートになる場合もならない場合もあることを指定します。|
   |**サポートされていません**|オブジェクトでトランザクションを除外することを指定します。 コンポーネント属性マクロ custom(TLBATTR_TRANS_NOTSUPP,0) を .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) に追加します。|
   |**新しいものが必要**|コンポーネント属性マクロ custom(TLBATTR_TRANS_REQNEW,0) を .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) に追加して、オブジェクトが常にトランザクション ストリームのルートになることを指定します。|

::: moniker-end

## <a name="see-also"></a>関連項目

[ATL COM+ 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[ATL COM+ 1.0 コンポーネント](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
