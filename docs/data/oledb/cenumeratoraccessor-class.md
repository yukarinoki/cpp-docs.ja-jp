---
title: CEnumeratorAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
ms.openlocfilehash: d85f630a01ab7e2a07035a8a304a56be91eca8a9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545631"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor クラス

[CEnumerator](../../data/oledb/cenumerator-class.md)によって使用され、列挙子行セットからデータにアクセスします。

## <a name="syntax"></a>構文

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_bIsParent](#bisparent)|行が列挙子である場合に、列挙子が親列挙子であるかどうかを示す変数。|
|[m_nType](#ntype)|行でデータソースまたは列挙子が記述されているかどうかを示す変数。|
|[m_szDescription](#szdescription)|データソースまたは列挙子の説明。|
|[m_szName](#szname)|データソースまたは列挙子の名前。|
|[m_szParseName](#szparsename)|データソースまたは列挙子のモニカーを取得するために[Iparsedisplayname](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname)に渡す文字列。|

## <a name="remarks"></a>コメント

この行セットは、現在の列挙子から参照できるデータソースと列挙子で構成されます。

## <a name="cenumeratoraccessorm_bisparent"></a><a name="bisparent"></a>CEnumeratorAccessor:: m_bIsParent

行が列挙子である場合に、列挙子が親列挙子であるかどうかを示す変数。

### <a name="syntax"></a>構文

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>コメント

詳細については、 *OLE DB プログラマーリファレンス*の「 [Isourcesrowset を:: getsourcesrowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) 」を参照してください。

## <a name="cenumeratoraccessorm_ntype"></a><a name="ntype"></a>CEnumeratorAccessor:: m_nType

行でデータソースまたは列挙子が記述されているかどうかを示す変数。

### <a name="syntax"></a>構文

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>コメント

詳細については、 *OLE DB プログラマーリファレンス*の「 [Isourcesrowset を:: getsourcesrowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) 」を参照してください。

## <a name="cenumeratoraccessorm_szdescription"></a><a name="szdescription"></a>CEnumeratorAccessor:: m_szDescription

データソースまたは列挙子の説明。

### <a name="syntax"></a>構文

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>コメント

詳細については、 *OLE DB プログラマーリファレンス*の「 [Isourcesrowset を:: getsourcesrowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) 」を参照してください。

## <a name="cenumeratoraccessorm_szname"></a><a name="szname"></a>CEnumeratorAccessor:: m_szName

データソースまたは列挙子の名前。

### <a name="syntax"></a>構文

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>コメント

詳細については、 *OLE DB プログラマーリファレンス*の「 [Isourcesrowset を:: getsourcesrowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) 」を参照してください。

## <a name="cenumeratoraccessorm_szparsename"></a><a name="szparsename"></a>CEnumeratorAccessor:: m_szParseName

データソースまたは列挙子のモニカーを取得するために[Iparsedisplayname](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname)に渡す文字列。

### <a name="syntax"></a>構文

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>コメント

詳細については、 *OLE DB プログラマーリファレンス*の「 [Isourcesrowset を:: getsourcesrowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)