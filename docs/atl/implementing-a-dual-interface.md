---
title: デュアル インターフェイス (ATL) の実装
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: a85597adad045bee3edb5cc3ed63c72a22fa08fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319465"
---
# <a name="implementing-a-dual-interface"></a>デュアル インターフェイスの実装

デュアル インターフェイスでは、メソッドの既定の実装を提供する[クラス、IDispatchImpl](../atl/reference/idispatchimpl-class.md)クラス`IDispatch`を使用してデュアル インターフェイスを実装できます。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

このクラスを使用するには、次の手順に従います。

- タイプ ライブラリでデュアル インターフェイスを定義します。

- クラスを派生させる (`IDispatchImpl`インターフェイスとタイプ ライブラリに関する情報をテンプレート引数として渡す)。

- を通じて`QueryInterface`デュアル インターフェイスを公開するエントリ (または複数のエントリ) を COM マップに追加します。

- クラスにインターフェイスの vtable 部分を実装します。

- インターフェイス定義を含むタイプ ライブラリが実行時にオブジェクトで使用できることを確認します。

## <a name="atl-simple-object-wizard"></a>ATL シンプル オブジェクト ウィザード

新しいインターフェイスと実装する新しいクラスを作成する場合は[、[ATL クラスの追加] ダイアログ ボックス](../ide/add-class-dialog-box.md)、および[ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)を使用します。

## <a name="implement-interface-wizard"></a>インターフェイス実装ウィザード

既存のインターフェイスがある場合は、[インターフェイス実装ウィザード](../atl/reference/adding-a-new-interface-in-an-atl-project.md)を使用して、必要な基本クラス、COM マップ エントリ、およびスケルトン メソッドの実装を既存のクラスに追加できます。

> [!NOTE]
> 生成された基本クラスを調整して、タイプ ライブラリのメジャー バージョン番号とマイナー バージョン番号をテンプレート引数として基本クラスに`IDispatchImpl`渡す必要がある場合があります。 インターフェイスの実装ウィザードでは、タイプ ライブラリのバージョン番号はチェックされません。

## <a name="implementing-idispatch"></a>IDispatch の実装

対応する`IDispatchImpl`デュアル インターフェイスを記述するタイプ ライブラリがある限り、COM マップで適切なエントリを指定するだけで 、基本クラスを使用して、COM_INTERFACE_ENTRY2[または](reference/com-interface-entry-macros.md#com_interface_entry2)[COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid)マクロを使用して、dispinterface の実装を提供できます。 たとえば、この方法でインターフェイスを`IDispatch`実装することは非常に一般的です。 ATL シンプル オブジェクト ウィザードとインターフェイス実装ウィザードは、この方法で`IDispatch`実装することを前提としているため、適切なエントリがマップに追加されます。

> [!NOTE]
> ATL には、互換性のあるデュアル インターフェイスの定義を含むタイプ ライブラリを必要とせずに、disp インターフェイスを実装するのに役立つ[IDispEventImpl](../atl/reference/idispeventimpl-class.md)クラスと[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)クラスが用意されています。

## <a name="see-also"></a>関連項目

[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)
