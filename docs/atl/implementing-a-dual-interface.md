---
title: デュアルインターフェイスの実装 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: 97d8cd912c85a74f3550a9ca6c7b87a9717d4075
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499549"
---
# <a name="implementing-a-dual-interface"></a>デュアルインターフェイスの実装

[IDispatchImpl](../atl/reference/idispatchimpl-class.md)クラスを使用してデュアルインターフェイスを実装できます。これにより、デュアルインターフェイスのメソッドの既定の実装が提供され `IDispatch` ます。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

このクラスを使用するには:

- タイプライブラリでデュアルインターフェイスを定義します。

- 特殊化されたからクラスを派生させ `IDispatchImpl` ます (インターフェイスとタイプライブラリに関する情報をテンプレート引数として渡します)。

- を介してデュアルインターフェイスを公開するために、エントリ (またはエントリ) を COM マップに追加 `QueryInterface` します。

- インターフェイスの vtable 部分をクラスに実装します。

- インターフェイス定義が含まれているタイプライブラリを実行時にオブジェクトで使用できることを確認します。

## <a name="atl-simple-object-wizard"></a>ATL シンプル オブジェクト ウィザード

新しいインターフェイスと、それを実装する新しいクラスを作成する場合は、[ [Atl クラスの追加] ダイアログボックス](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box)を使用して、 [Atl シンプルオブジェクトウィザード](../atl/reference/atl-simple-object-wizard.md)を使用できます。

## <a name="implement-interface-wizard"></a>インターフェイス実装ウィザード

既存のインターフェイスがある場合は、 [インターフェイスの実装ウィザード](../atl/reference/adding-a-new-interface-in-an-atl-project.md) を使用して、必要な基本クラス、COM マップエントリ、およびスケルトンメソッドの実装を既存のクラスに追加できます。

> [!NOTE]
> 生成された基本クラスを調整して、タイプライブラリのメジャーバージョン番号とマイナーバージョン番号をテンプレート引数として基底クラスに渡すことが必要になる場合があり `IDispatchImpl` ます。 インターフェイスの実装ウィザードでは、タイプライブラリのバージョン番号はチェックされません。

## <a name="implementing-idispatch"></a>IDispatch の実装

基底クラスを使用すると、 `IDispatchImpl` 対応するデュアルインターフェイスを記述するタイプライブラリがある限り、COM マップで ( [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) または [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) マクロを使用して) 適切なエントリを指定するだけで、ディスパッチインターフェイスの実装を提供できます。 たとえば、このようにインターフェイスを実装するのは非常に一般的です `IDispatch` 。 ATL シンプルオブジェクトウィザードとインターフェイスの実装ウィザードでは、どちらもこの方法でを実装することを想定しているので、 `IDispatch` 適切なエントリをマップに追加します。

> [!NOTE]
> ATL には、 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) クラスと [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) クラスが用意されており、互換性のあるデュアルインターフェイスの定義を含むタイプライブラリを必要とせずに、ディスパッチインターフェイスを実装するのに役立ちます。

## <a name="see-also"></a>関連項目

[デュアルインターフェイスと ATL](../atl/dual-interfaces-and-atl.md)
