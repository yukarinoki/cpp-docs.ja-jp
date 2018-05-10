---
title: デュアル インターフェイス (ATL) の実装 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34cc55e4466dba094bf70e734340b40237207f3c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-a-dual-interface"></a>デュアル インターフェイスの実装
使用して、デュアル インターフェイスを実装することができます、 [IDispatchImpl](../atl/reference/idispatchimpl-class.md)の既定の実装を提供するクラス、`IDispatch`デュアル インターフェイスのメソッドです。 詳細については、「 [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)」を参照してください。  
  
 このクラスを使用します。  
  
-   タイプ ライブラリで、デュアル インターフェイスを定義します。  
  
-   特化したクラスからの派生クラス`IDispatchImpl`(テンプレート引数として、インターフェイスとタイプ ライブラリに関する情報を渡す)。  
  
-   デュアル インターフェイスを介して公開する COM マップ エントリ (またはエントリ) を追加`QueryInterface`です。  
  
-   クラスの vtable 一部インターフェイスを実装します。  
  
-   実行時に、インターフェイス定義が含まれるタイプ ライブラリが、オブジェクトで使用できることを確認します。  
  
## <a name="atl-simple-object-wizard"></a>ATL シンプル オブジェクト ウィザード  
 新しいインターフェイスとそれを実装する新しいクラスを作成する場合は、使用、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)、し、 [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)です。  
  
## <a name="implement-interface-wizard"></a>インターフェイス実装ウィザード  
 既存のインターフェイスがあれば、行うこともできます、[インターフェイス実装ウィザード](../atl/reference/adding-a-new-interface-in-an-atl-project.md)を既存のクラスに必要な基本クラス、COM マップ エントリ、およびメソッドのスケルトンの実装を追加します。  
  
> [!NOTE]
>  タイプ ライブラリのメジャーおよびマイナー バージョン番号は、テンプレート引数として渡されるように、生成された基本クラスを調整する必要があります、`IDispatchImpl`基本クラスです。 インターフェイスの実装ウィザードでは、タイプ ライブラリのバージョン番号をチェックしません。  
  
## <a name="implementing-idispatch"></a>IDispatch を実装します。  
 使用することができます、`IDispatchImpl`基本 COM マップに適切なエントリを指定するだけでディスパッチ インターフェイスの実装を提供するクラス (を使用して、 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2)または[COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid)マクロ)、対応するデュアル インターフェイスを記述するタイプ ライブラリがある限り、します。 実装する非常に一般的である、`IDispatch`インターフェイスこの方法の例を示します。 ATL シンプル オブジェクト ウィザードとインターフェイス実装ウィザードを実装することを想定両方`IDispatch`この方法でためそれらが適切なエントリ、マップに追加します。  
  
> [!NOTE]
>  ATL には、 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)と[されます](../atl/reference/idispeventsimpleimpl-class.md)互換性デュアル インターフェイスの定義が含まれるタイプ ライブラリを必要とせずにディスパッチ インターフェイスを実装するクラスが用意されます。  
  
## <a name="see-also"></a>関連項目  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

