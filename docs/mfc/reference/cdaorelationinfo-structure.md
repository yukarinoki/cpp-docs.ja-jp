---
description: '詳細については、次を参照してください: CDaoRelationInfo 構造体'
title: CDaoRelationInfo 構造体
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: efcc880d30dd18108005d9c4f265238b81551532
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222243"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 構造体

この `CDaoRelationInfo` 構造体には、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) オブジェクト内の2つのテーブルのフィールド間に定義されたリレーションシップに関する情報が含まれます。

## <a name="syntax"></a>構文

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
    CString m_strName;                      // Primary
    CString m_strTable;                     // Primary
    CString m_strForeignTable;              // Primary
    long m_lAttributes;                     // Secondary
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
リレーションシップオブジェクトの名前を一意に識別します。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_strTable*<br/>
リレーションシップ内の主テーブルの名前を示します。

*m_strForeignTable*<br/>
リレーションシップ内の外部テーブルの名前を示します。 外部テーブルは、外部キーを格納するために使用されるテーブルです。 通常、外部テーブルを使用して、参照整合性を確立または適用します。 外部テーブルは、通常、一対多のリレーションシップの "多" の側にあります。 外部テーブルの例としては、米国またはカナダの州または顧客の注文のコードを含むテーブルがあります。

*m_lAttributes*<br/>
リレーションシップの種類に関する情報を格納します。 このメンバーの値には、次のいずれかを指定できます。

- `dbRelationUnique` リレーションシップは一対一です。

- `dbRelationDontEnforce` リレーションシップは強制されません (参照整合性はありません)。

- `dbRelationInherited` リレーションシップは、2つのアタッチされたテーブルを含む最新複数データベースに存在します。

- `dbRelationLeft` リレーションシップは左結合です。 左外部結合には、2つのテーブルの最初の (左側の) からのすべてのレコードが含まれます。これは、2番目 (右側) のテーブルにレコードの一致する値がない場合でも同様です。

- `dbRelationRight` リレーションシップは、右結合です。 右外部結合には、2つのテーブルの2番目 (右側) のすべてのレコードが含まれます。最初の (左側の) テーブルのレコードに一致する値がない場合でも同様です。

- `dbRelationUpdateCascade` 更新は連鎖します。

- `dbRelationDeleteCascade` 削除は連鎖します。

*m_pFieldInfos*<br/>
[CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)構造体の配列へのポインター。 配列には、リレーションシップのフィールドごとに1つのオブジェクトが格納されます。 `m_nFields`データメンバーは、配列要素の数を示します。

*m_nFields*<br/>
`CDaoRelationFieldInfo`データメンバー内のオブジェクトの数 `m_pFieldInfos` 。

## <a name="remarks"></a>解説

上のプライマリとセカンダリへの参照は、クラスの [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) メンバー関数によって情報がどのように返されるかを示し `CDaoDatabase` ます。

Relation オブジェクトは MFC クラスでは表されません。 代わりに、クラスの MFC オブジェクトの基になる DAO オブジェクトは、 `CDaoDatabase` リレーションシップオブジェクトのコレクションを保持します。 `CDaoDatabase` は、リレーションシップ情報の一部の項目にアクセスするメンバー関数を提供し `CDaoRelationInfo` ます。また、 `GetRelationInfo` 包含データベースオブジェクトのメンバー関数を呼び出すことによって、オブジェクトを使用して一度にすべてのオブジェクトにアクセスすることもできます。

[CDaoDatabase:: GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)メンバー関数によって取得された情報は、構造体に格納され `CDaoRelationInfo` ます。 `CDaoRelationInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoRelationInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[CDaoRelationFieldInfo 構造体](../../mfc/reference/cdaorelationfieldinfo-structure.md)
