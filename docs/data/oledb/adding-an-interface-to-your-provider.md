---
title: プロバイダーへのインターフェイスの追加
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: c0452ca74509b65de3787af93bff41b3cb399c99
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033874"
---
# <a name="adding-an-interface-to-your-provider"></a>プロバイダーへのインターフェイスの追加

インターフェイスを追加するオブジェクトを決定する (データ ソース、行セット、コマンド、またはセッション オブジェクトの作成者は、通常、 **OLE DB プロバイダー ウィザード**)。 インターフェイスを追加する必要があるオブジェクトが、プロバイダーがサポートされていないものであることができます。 その場合は、実行、 **ATL OLE DB プロバイダー ウィザード**オブジェクトを作成します。 プロジェクトを右クリックして**クラス ビュー**、 をクリックして**追加** > **新しい項目の**メニューから、次のように選択します**インストール済み** > 。 **Visual C** > **ATL**、 をクリックし、 **ATL OLEDB プロバイダー**します。 インターフェイスのコードの別のディレクトリを配置し、プロバイダーのプロジェクトに、ファイルをコピーする場合があります。

インターフェイスをサポートする新しいクラスを作成する場合は、そのクラスから継承するオブジェクトをください。 たとえば、クラスを追加する場合があります`IRowsetIndexImpl`行セット オブジェクトに。

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

COM_INTERFACE_ENTRY マクロを使用してオブジェクトで COM_MAP にインターフェイスを追加します。 マップがない場合は、1 つを作成します。 例えば:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

行セット オブジェクトのチェーン、親のマップ オブジェクトのオブジェクトが親クラスに委任できるようにします。 この例では、マップに COM_INTERFACE_ENTRY_CHAIN マクロを追加します。

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)