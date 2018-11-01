---
title: プロバイダーへのインターフェイスの追加
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: 295a7955b78918d6281a28b616f201869f37b01e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488674"
---
# <a name="adding-an-interface-to-your-provider"></a>プロバイダーへのインターフェイスの追加

(通常はデータ ソース、行セット、コマンド、またはセッション オブジェクトに OLE DB プロバイダー ウィザードで作成された) インターフェイスを追加するオブジェクトを決定します。 インターフェイスを追加する必要があるオブジェクトが、プロバイダーが現在サポートされていない 1 つであることができます。 その場合は、ATL OLE DB プロバイダー ウィザード、オブジェクトを作成するを実行します。 クラス ビューでプロジェクトを右クリックし、をクリックして**クラスの追加**から、**追加** メニューをクリック**ATL OLE DB Provider**します。 インターフェイスのコードの別のディレクトリを配置し、プロバイダーのプロジェクトに、ファイルをコピーする場合があります。

インターフェイスをサポートする新しいクラスを作成する場合は、そのクラスから継承するオブジェクトをください。 たとえば、クラスを追加する場合があります**IRowsetIndexImpl**行セット オブジェクトに。

```cpp
template <class Creator>
class CAgentRowset :
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,
    public IRowsetIndexImpl< ... >
```

インターフェイスを追加**COM_MAP** COM_INTERFACE_ENTRY マクロを使用してオブジェクトにします。 マップがない場合は、1 つを作成します。 例えば:

```cpp
BEGIN_COM_MAP(CAgentRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

行セット オブジェクトのチェーン、親のマップ オブジェクトのオブジェクトが親クラスに委任できるようにします。 この例では、マップに COM_INTERFACE_ENTRY_CHAIN マクロを追加します。

```cpp
BEGIN_COM_MAP(CAgentRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)