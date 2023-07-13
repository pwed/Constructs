# pwed-cdk

[![release](https://github.com/pwed/pwed-cdk/actions/workflows/release.yml/badge.svg)](https://github.com/pwed/pwed-cdk/actions/workflows/release.yml)
![npm](https://img.shields.io/npm/v/pwed-cdk?color=%2368A063)
![PyPI](https://img.shields.io/pypi/v/pwed-cdk?color=%23306998)


A library of AWS CDK constructs that I have made for fun.

[Docs](/API.md)

## Disclaimer

This repository is in early development and can be restructured at any time.
A much higher level of stability will be targeted after 1.0.0 release

## Install

```sh
## Node
npm i pwed-cdk

## Python
pip install pwed-cdk
```

## Constructs

1. static-site
   1. Is a simple static site that will automatically upload assets to s3 and serve them with CloudFront. Any pushed changed files will get invalidated from the CloudFront cache.
2. bastion
   1. windows-instance
      1. A windows instance that can be signed into using fleet manager for a zero surface area RDP bastion.
   2. permission-set
      1. AWS SSO permission set with the minimum permissions to give access to SSM and Fleet Manager
      2. Can be locked down with Tags if you want environment level access

## Coming soon

1. Non SSO based access for bastion
2. Hugo extension for static-site to auto build and deploy your static site

# API Reference <a name="API Reference" id="api-reference"></a>

## Constructs <a name="Constructs" id="Constructs"></a>

### BastionAccessPolicy <a name="BastionAccessPolicy" id="pwed-cdk.bastion.BastionAccessPolicy"></a>

#### Initializers <a name="Initializers" id="pwed-cdk.bastion.BastionAccessPolicy.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

new bastion.BastionAccessPolicy(scope: Construct, id: string, props?: BastionAccessPolicyProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.bastion.BastionAccessPolicyProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.bastion.BastionAccessPolicy.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.bastion.BastionAccessPolicy.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Optional</sup> <a name="props" id="pwed-cdk.bastion.BastionAccessPolicy.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.bastion.BastionAccessPolicyProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.toString">toString</a></code> | Returns a string representation of this construct. |

---

##### `toString` <a name="toString" id="pwed-cdk.bastion.BastionAccessPolicy.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.bastion.BastionAccessPolicy.isConstruct"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.BastionAccessPolicy.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.bastion.BastionAccessPolicy.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicy.property.policy">policy</a></code> | <code>aws-cdk-lib.aws_iam.PolicyDocument</code> | *No description.* |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.bastion.BastionAccessPolicy.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---

##### `policy`<sup>Required</sup> <a name="policy" id="pwed-cdk.bastion.BastionAccessPolicy.property.policy"></a>

```typescript
public readonly policy: PolicyDocument;
```

- *Type:* aws-cdk-lib.aws_iam.PolicyDocument

---


### BastionPermissionSet <a name="BastionPermissionSet" id="pwed-cdk.bastion.BastionPermissionSet"></a>

#### Initializers <a name="Initializers" id="pwed-cdk.bastion.BastionPermissionSet.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

new bastion.BastionPermissionSet(scope: Construct, id: string, props: BastionPermissionSetProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.bastion.BastionPermissionSetProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.bastion.BastionPermissionSet.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.bastion.BastionPermissionSet.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Required</sup> <a name="props" id="pwed-cdk.bastion.BastionPermissionSet.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.bastion.BastionPermissionSetProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.toString">toString</a></code> | Returns a string representation of this construct. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.applyRemovalPolicy">applyRemovalPolicy</a></code> | Apply the given removal policy to this resource. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.assign">assign</a></code> | *No description.* |

---

##### `toString` <a name="toString" id="pwed-cdk.bastion.BastionPermissionSet.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

##### `applyRemovalPolicy` <a name="applyRemovalPolicy" id="pwed-cdk.bastion.BastionPermissionSet.applyRemovalPolicy"></a>

```typescript
public applyRemovalPolicy(policy: RemovalPolicy): void
```

Apply the given removal policy to this resource.

The Removal Policy controls what happens to this resource when it stops
being managed by CloudFormation, either because you've removed it from the
CDK application or because you've made a change that requires the resource
to be replaced.

The resource can be deleted (`RemovalPolicy.DESTROY`), or left in your AWS
account for data recovery and cleanup later (`RemovalPolicy.RETAIN`).

###### `policy`<sup>Required</sup> <a name="policy" id="pwed-cdk.bastion.BastionPermissionSet.applyRemovalPolicy.parameter.policy"></a>

- *Type:* aws-cdk-lib.RemovalPolicy

---

##### `assign` <a name="assign" id="pwed-cdk.bastion.BastionPermissionSet.assign"></a>

```typescript
public assign(accountId: string, principalId: string, principalType: string): void
```

###### `accountId`<sup>Required</sup> <a name="accountId" id="pwed-cdk.bastion.BastionPermissionSet.assign.parameter.accountId"></a>

- *Type:* string

---

###### `principalId`<sup>Required</sup> <a name="principalId" id="pwed-cdk.bastion.BastionPermissionSet.assign.parameter.principalId"></a>

- *Type:* string

---

###### `principalType`<sup>Required</sup> <a name="principalType" id="pwed-cdk.bastion.BastionPermissionSet.assign.parameter.principalType"></a>

- *Type:* string

---

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.isOwnedResource">isOwnedResource</a></code> | Returns true if the construct was created by CDK, and false otherwise. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.isResource">isResource</a></code> | Check whether the given construct is a Resource. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.bastion.BastionPermissionSet.isConstruct"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.BastionPermissionSet.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.bastion.BastionPermissionSet.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

##### `isOwnedResource` <a name="isOwnedResource" id="pwed-cdk.bastion.BastionPermissionSet.isOwnedResource"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.BastionPermissionSet.isOwnedResource(construct: IConstruct)
```

Returns true if the construct was created by CDK, and false otherwise.

###### `construct`<sup>Required</sup> <a name="construct" id="pwed-cdk.bastion.BastionPermissionSet.isOwnedResource.parameter.construct"></a>

- *Type:* constructs.IConstruct

---

##### `isResource` <a name="isResource" id="pwed-cdk.bastion.BastionPermissionSet.isResource"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.BastionPermissionSet.isResource(construct: IConstruct)
```

Check whether the given construct is a Resource.

###### `construct`<sup>Required</sup> <a name="construct" id="pwed-cdk.bastion.BastionPermissionSet.isResource.parameter.construct"></a>

- *Type:* constructs.IConstruct

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.property.env">env</a></code> | <code>aws-cdk-lib.ResourceEnvironment</code> | The environment this resource belongs to. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.property.stack">stack</a></code> | <code>aws-cdk-lib.Stack</code> | The stack in which this resource is defined. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSet.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | *No description.* |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.bastion.BastionPermissionSet.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---

##### `env`<sup>Required</sup> <a name="env" id="pwed-cdk.bastion.BastionPermissionSet.property.env"></a>

```typescript
public readonly env: ResourceEnvironment;
```

- *Type:* aws-cdk-lib.ResourceEnvironment

The environment this resource belongs to.

For resources that are created and managed by the CDK
(generally, those created by creating new class instances like Role, Bucket, etc.),
this is always the same as the environment of the stack they belong to;
however, for imported resources
(those obtained from static methods like fromRoleArn, fromBucketName, etc.),
that might be different than the stack they were imported into.

---

##### `stack`<sup>Required</sup> <a name="stack" id="pwed-cdk.bastion.BastionPermissionSet.property.stack"></a>

```typescript
public readonly stack: Stack;
```

- *Type:* aws-cdk-lib.Stack

The stack in which this resource is defined.

---

##### `securityTag`<sup>Required</sup> <a name="securityTag" id="pwed-cdk.bastion.BastionPermissionSet.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag

---


### LinuxBastion <a name="LinuxBastion" id="pwed-cdk.bastion.LinuxBastion"></a>

- *Implements:* aws-cdk-lib.aws_ec2.IInstance

#### Initializers <a name="Initializers" id="pwed-cdk.bastion.LinuxBastion.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

new bastion.LinuxBastion(scope: Construct, id: string, props: LinuxBastionProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.bastion.LinuxBastionProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.bastion.LinuxBastion.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.bastion.LinuxBastion.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Required</sup> <a name="props" id="pwed-cdk.bastion.LinuxBastion.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.bastion.LinuxBastionProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.toString">toString</a></code> | Returns a string representation of this construct. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.applyRemovalPolicy">applyRemovalPolicy</a></code> | Apply the given removal policy to this resource. |

---

##### `toString` <a name="toString" id="pwed-cdk.bastion.LinuxBastion.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

##### `applyRemovalPolicy` <a name="applyRemovalPolicy" id="pwed-cdk.bastion.LinuxBastion.applyRemovalPolicy"></a>

```typescript
public applyRemovalPolicy(policy: RemovalPolicy): void
```

Apply the given removal policy to this resource.

The Removal Policy controls what happens to this resource when it stops
being managed by CloudFormation, either because you've removed it from the
CDK application or because you've made a change that requires the resource
to be replaced.

The resource can be deleted (`RemovalPolicy.DESTROY`), or left in your AWS
account for data recovery and cleanup later (`RemovalPolicy.RETAIN`).

###### `policy`<sup>Required</sup> <a name="policy" id="pwed-cdk.bastion.LinuxBastion.applyRemovalPolicy.parameter.policy"></a>

- *Type:* aws-cdk-lib.RemovalPolicy

---

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.isOwnedResource">isOwnedResource</a></code> | Returns true if the construct was created by CDK, and false otherwise. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.isResource">isResource</a></code> | Check whether the given construct is a Resource. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.bastion.LinuxBastion.isConstruct"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.LinuxBastion.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.bastion.LinuxBastion.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

##### `isOwnedResource` <a name="isOwnedResource" id="pwed-cdk.bastion.LinuxBastion.isOwnedResource"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.LinuxBastion.isOwnedResource(construct: IConstruct)
```

Returns true if the construct was created by CDK, and false otherwise.

###### `construct`<sup>Required</sup> <a name="construct" id="pwed-cdk.bastion.LinuxBastion.isOwnedResource.parameter.construct"></a>

- *Type:* constructs.IConstruct

---

##### `isResource` <a name="isResource" id="pwed-cdk.bastion.LinuxBastion.isResource"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.LinuxBastion.isResource(construct: IConstruct)
```

Check whether the given construct is a Resource.

###### `construct`<sup>Required</sup> <a name="construct" id="pwed-cdk.bastion.LinuxBastion.isResource.parameter.construct"></a>

- *Type:* constructs.IConstruct

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.env">env</a></code> | <code>aws-cdk-lib.ResourceEnvironment</code> | The environment this resource belongs to. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.stack">stack</a></code> | <code>aws-cdk-lib.Stack</code> | The stack in which this resource is defined. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.connections">connections</a></code> | <code>aws-cdk-lib.aws_ec2.Connections</code> | The network connections associated with this resource. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.grantPrincipal">grantPrincipal</a></code> | <code>aws-cdk-lib.aws_iam.IPrincipal</code> | The principal to grant permissions to. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.instanceAvailabilityZone">instanceAvailabilityZone</a></code> | <code>string</code> | The availability zone the instance was launched in. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.instanceId">instanceId</a></code> | <code>string</code> | The instance's ID. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.instancePrivateDnsName">instancePrivateDnsName</a></code> | <code>string</code> | Private DNS name for this instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.instancePrivateIp">instancePrivateIp</a></code> | <code>string</code> | Private IP for this instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.instancePublicDnsName">instancePublicDnsName</a></code> | <code>string</code> | Publicly-routable DNS name for this instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.instancePublicIp">instancePublicIp</a></code> | <code>string</code> | Publicly-routable IP  address for this instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.role">role</a></code> | <code>aws-cdk-lib.aws_iam.IRole</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.LinuxBastion.property.securityGroup">securityGroup</a></code> | <code>aws-cdk-lib.aws_ec2.ISecurityGroup</code> | *No description.* |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.bastion.LinuxBastion.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---

##### `env`<sup>Required</sup> <a name="env" id="pwed-cdk.bastion.LinuxBastion.property.env"></a>

```typescript
public readonly env: ResourceEnvironment;
```

- *Type:* aws-cdk-lib.ResourceEnvironment

The environment this resource belongs to.

For resources that are created and managed by the CDK
(generally, those created by creating new class instances like Role, Bucket, etc.),
this is always the same as the environment of the stack they belong to;
however, for imported resources
(those obtained from static methods like fromRoleArn, fromBucketName, etc.),
that might be different than the stack they were imported into.

---

##### `stack`<sup>Required</sup> <a name="stack" id="pwed-cdk.bastion.LinuxBastion.property.stack"></a>

```typescript
public readonly stack: Stack;
```

- *Type:* aws-cdk-lib.Stack

The stack in which this resource is defined.

---

##### `connections`<sup>Required</sup> <a name="connections" id="pwed-cdk.bastion.LinuxBastion.property.connections"></a>

```typescript
public readonly connections: Connections;
```

- *Type:* aws-cdk-lib.aws_ec2.Connections

The network connections associated with this resource.

---

##### `grantPrincipal`<sup>Required</sup> <a name="grantPrincipal" id="pwed-cdk.bastion.LinuxBastion.property.grantPrincipal"></a>

```typescript
public readonly grantPrincipal: IPrincipal;
```

- *Type:* aws-cdk-lib.aws_iam.IPrincipal

The principal to grant permissions to.

---

##### `instanceAvailabilityZone`<sup>Required</sup> <a name="instanceAvailabilityZone" id="pwed-cdk.bastion.LinuxBastion.property.instanceAvailabilityZone"></a>

```typescript
public readonly instanceAvailabilityZone: string;
```

- *Type:* string

The availability zone the instance was launched in.

---

##### `instanceId`<sup>Required</sup> <a name="instanceId" id="pwed-cdk.bastion.LinuxBastion.property.instanceId"></a>

```typescript
public readonly instanceId: string;
```

- *Type:* string

The instance's ID.

---

##### `instancePrivateDnsName`<sup>Required</sup> <a name="instancePrivateDnsName" id="pwed-cdk.bastion.LinuxBastion.property.instancePrivateDnsName"></a>

```typescript
public readonly instancePrivateDnsName: string;
```

- *Type:* string

Private DNS name for this instance.

---

##### `instancePrivateIp`<sup>Required</sup> <a name="instancePrivateIp" id="pwed-cdk.bastion.LinuxBastion.property.instancePrivateIp"></a>

```typescript
public readonly instancePrivateIp: string;
```

- *Type:* string

Private IP for this instance.

---

##### `instancePublicDnsName`<sup>Required</sup> <a name="instancePublicDnsName" id="pwed-cdk.bastion.LinuxBastion.property.instancePublicDnsName"></a>

```typescript
public readonly instancePublicDnsName: string;
```

- *Type:* string

Publicly-routable DNS name for this instance.

(May be an empty string if the instance does not have a public name).

---

##### `instancePublicIp`<sup>Required</sup> <a name="instancePublicIp" id="pwed-cdk.bastion.LinuxBastion.property.instancePublicIp"></a>

```typescript
public readonly instancePublicIp: string;
```

- *Type:* string

Publicly-routable IP  address for this instance.

(May be an empty string if the instance does not have a public IP).

---

##### `role`<sup>Required</sup> <a name="role" id="pwed-cdk.bastion.LinuxBastion.property.role"></a>

```typescript
public readonly role: IRole;
```

- *Type:* aws-cdk-lib.aws_iam.IRole

---

##### `securityGroup`<sup>Required</sup> <a name="securityGroup" id="pwed-cdk.bastion.LinuxBastion.property.securityGroup"></a>

```typescript
public readonly securityGroup: ISecurityGroup;
```

- *Type:* aws-cdk-lib.aws_ec2.ISecurityGroup

---


### ScheduleShutdown <a name="ScheduleShutdown" id="pwed-cdk.bastion.ScheduleShutdown"></a>

#### Initializers <a name="Initializers" id="pwed-cdk.bastion.ScheduleShutdown.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

new bastion.ScheduleShutdown(scope: Construct, id: string, props?: ScheduleShutdownProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdown.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdown.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdown.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.bastion.ScheduleShutdownProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.bastion.ScheduleShutdown.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.bastion.ScheduleShutdown.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Optional</sup> <a name="props" id="pwed-cdk.bastion.ScheduleShutdown.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.bastion.ScheduleShutdownProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdown.toString">toString</a></code> | Returns a string representation of this construct. |

---

##### `toString` <a name="toString" id="pwed-cdk.bastion.ScheduleShutdown.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdown.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.bastion.ScheduleShutdown.isConstruct"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.ScheduleShutdown.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.bastion.ScheduleShutdown.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdown.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.bastion.ScheduleShutdown.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---


### StaticSite <a name="StaticSite" id="pwed-cdk.static_site.StaticSite"></a>

#### Initializers <a name="Initializers" id="pwed-cdk.static_site.StaticSite.Initializer"></a>

```typescript
import { static_site } from 'pwed-cdk'

new static_site.StaticSite(scope: Construct, id: string, props: StaticSiteProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.static_site.StaticSite.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSite.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSite.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.static_site.StaticSiteProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.static_site.StaticSite.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.static_site.StaticSite.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Required</sup> <a name="props" id="pwed-cdk.static_site.StaticSite.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.static_site.StaticSiteProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.static_site.StaticSite.toString">toString</a></code> | Returns a string representation of this construct. |

---

##### `toString` <a name="toString" id="pwed-cdk.static_site.StaticSite.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.static_site.StaticSite.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.static_site.StaticSite.isConstruct"></a>

```typescript
import { static_site } from 'pwed-cdk'

static_site.StaticSite.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.static_site.StaticSite.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.static_site.StaticSite.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |
| <code><a href="#pwed-cdk.static_site.StaticSite.property.distribution">distribution</a></code> | <code>aws-cdk-lib.aws_cloudfront.IDistribution</code> | *No description.* |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.static_site.StaticSite.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---

##### `distribution`<sup>Required</sup> <a name="distribution" id="pwed-cdk.static_site.StaticSite.property.distribution"></a>

```typescript
public readonly distribution: IDistribution;
```

- *Type:* aws-cdk-lib.aws_cloudfront.IDistribution

---


### Ttl <a name="Ttl" id="pwed-cdk.ttl.Ttl"></a>

#### Initializers <a name="Initializers" id="pwed-cdk.ttl.Ttl.Initializer"></a>

```typescript
import { ttl } from 'pwed-cdk'

new ttl.Ttl(scope: Construct, id: string, props: TtlProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.ttl.Ttl.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.ttl.Ttl.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.ttl.Ttl.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.ttl.TtlProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.ttl.Ttl.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.ttl.Ttl.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Required</sup> <a name="props" id="pwed-cdk.ttl.Ttl.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.ttl.TtlProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.ttl.Ttl.toString">toString</a></code> | Returns a string representation of this construct. |

---

##### `toString` <a name="toString" id="pwed-cdk.ttl.Ttl.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.ttl.Ttl.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.ttl.Ttl.isConstruct"></a>

```typescript
import { ttl } from 'pwed-cdk'

ttl.Ttl.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.ttl.Ttl.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.ttl.Ttl.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.ttl.Ttl.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---


### WindowsBastion <a name="WindowsBastion" id="pwed-cdk.bastion.WindowsBastion"></a>

- *Implements:* aws-cdk-lib.aws_ec2.IInstance

#### Initializers <a name="Initializers" id="pwed-cdk.bastion.WindowsBastion.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

new bastion.WindowsBastion(scope: Construct, id: string, props: WindowsBastionProps)
```

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.Initializer.parameter.scope">scope</a></code> | <code>constructs.Construct</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.Initializer.parameter.id">id</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.Initializer.parameter.props">props</a></code> | <code>pwed-cdk.bastion.WindowsBastionProps</code> | *No description.* |

---

##### `scope`<sup>Required</sup> <a name="scope" id="pwed-cdk.bastion.WindowsBastion.Initializer.parameter.scope"></a>

- *Type:* constructs.Construct

---

##### `id`<sup>Required</sup> <a name="id" id="pwed-cdk.bastion.WindowsBastion.Initializer.parameter.id"></a>

- *Type:* string

---

##### `props`<sup>Required</sup> <a name="props" id="pwed-cdk.bastion.WindowsBastion.Initializer.parameter.props"></a>

- *Type:* pwed-cdk.bastion.WindowsBastionProps

---

#### Methods <a name="Methods" id="Methods"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.toString">toString</a></code> | Returns a string representation of this construct. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.applyRemovalPolicy">applyRemovalPolicy</a></code> | Apply the given removal policy to this resource. |

---

##### `toString` <a name="toString" id="pwed-cdk.bastion.WindowsBastion.toString"></a>

```typescript
public toString(): string
```

Returns a string representation of this construct.

##### `applyRemovalPolicy` <a name="applyRemovalPolicy" id="pwed-cdk.bastion.WindowsBastion.applyRemovalPolicy"></a>

```typescript
public applyRemovalPolicy(policy: RemovalPolicy): void
```

Apply the given removal policy to this resource.

The Removal Policy controls what happens to this resource when it stops
being managed by CloudFormation, either because you've removed it from the
CDK application or because you've made a change that requires the resource
to be replaced.

The resource can be deleted (`RemovalPolicy.DESTROY`), or left in your AWS
account for data recovery and cleanup later (`RemovalPolicy.RETAIN`).

###### `policy`<sup>Required</sup> <a name="policy" id="pwed-cdk.bastion.WindowsBastion.applyRemovalPolicy.parameter.policy"></a>

- *Type:* aws-cdk-lib.RemovalPolicy

---

#### Static Functions <a name="Static Functions" id="Static Functions"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.isConstruct">isConstruct</a></code> | Checks if `x` is a construct. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.isOwnedResource">isOwnedResource</a></code> | Returns true if the construct was created by CDK, and false otherwise. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.isResource">isResource</a></code> | Check whether the given construct is a Resource. |

---

##### ~~`isConstruct`~~ <a name="isConstruct" id="pwed-cdk.bastion.WindowsBastion.isConstruct"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.WindowsBastion.isConstruct(x: any)
```

Checks if `x` is a construct.

###### `x`<sup>Required</sup> <a name="x" id="pwed-cdk.bastion.WindowsBastion.isConstruct.parameter.x"></a>

- *Type:* any

Any object.

---

##### `isOwnedResource` <a name="isOwnedResource" id="pwed-cdk.bastion.WindowsBastion.isOwnedResource"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.WindowsBastion.isOwnedResource(construct: IConstruct)
```

Returns true if the construct was created by CDK, and false otherwise.

###### `construct`<sup>Required</sup> <a name="construct" id="pwed-cdk.bastion.WindowsBastion.isOwnedResource.parameter.construct"></a>

- *Type:* constructs.IConstruct

---

##### `isResource` <a name="isResource" id="pwed-cdk.bastion.WindowsBastion.isResource"></a>

```typescript
import { bastion } from 'pwed-cdk'

bastion.WindowsBastion.isResource(construct: IConstruct)
```

Check whether the given construct is a Resource.

###### `construct`<sup>Required</sup> <a name="construct" id="pwed-cdk.bastion.WindowsBastion.isResource.parameter.construct"></a>

- *Type:* constructs.IConstruct

---

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.node">node</a></code> | <code>constructs.Node</code> | The tree node. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.env">env</a></code> | <code>aws-cdk-lib.ResourceEnvironment</code> | The environment this resource belongs to. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.stack">stack</a></code> | <code>aws-cdk-lib.Stack</code> | The stack in which this resource is defined. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.connections">connections</a></code> | <code>aws-cdk-lib.aws_ec2.Connections</code> | The network connections associated with this resource. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.grantPrincipal">grantPrincipal</a></code> | <code>aws-cdk-lib.aws_iam.IPrincipal</code> | The principal to grant permissions to. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.instanceAvailabilityZone">instanceAvailabilityZone</a></code> | <code>string</code> | The availability zone the instance was launched in. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.instanceId">instanceId</a></code> | <code>string</code> | The instance's ID. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.instancePrivateDnsName">instancePrivateDnsName</a></code> | <code>string</code> | Private DNS name for this instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.instancePrivateIp">instancePrivateIp</a></code> | <code>string</code> | Private IP for this instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.instancePublicDnsName">instancePublicDnsName</a></code> | <code>string</code> | Publicly-routable DNS name for this instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.instancePublicIp">instancePublicIp</a></code> | <code>string</code> | Publicly-routable IP  address for this instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.role">role</a></code> | <code>aws-cdk-lib.aws_iam.IRole</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.WindowsBastion.property.securityGroup">securityGroup</a></code> | <code>aws-cdk-lib.aws_ec2.ISecurityGroup</code> | *No description.* |

---

##### `node`<sup>Required</sup> <a name="node" id="pwed-cdk.bastion.WindowsBastion.property.node"></a>

```typescript
public readonly node: Node;
```

- *Type:* constructs.Node

The tree node.

---

##### `env`<sup>Required</sup> <a name="env" id="pwed-cdk.bastion.WindowsBastion.property.env"></a>

```typescript
public readonly env: ResourceEnvironment;
```

- *Type:* aws-cdk-lib.ResourceEnvironment

The environment this resource belongs to.

For resources that are created and managed by the CDK
(generally, those created by creating new class instances like Role, Bucket, etc.),
this is always the same as the environment of the stack they belong to;
however, for imported resources
(those obtained from static methods like fromRoleArn, fromBucketName, etc.),
that might be different than the stack they were imported into.

---

##### `stack`<sup>Required</sup> <a name="stack" id="pwed-cdk.bastion.WindowsBastion.property.stack"></a>

```typescript
public readonly stack: Stack;
```

- *Type:* aws-cdk-lib.Stack

The stack in which this resource is defined.

---

##### `connections`<sup>Required</sup> <a name="connections" id="pwed-cdk.bastion.WindowsBastion.property.connections"></a>

```typescript
public readonly connections: Connections;
```

- *Type:* aws-cdk-lib.aws_ec2.Connections

The network connections associated with this resource.

---

##### `grantPrincipal`<sup>Required</sup> <a name="grantPrincipal" id="pwed-cdk.bastion.WindowsBastion.property.grantPrincipal"></a>

```typescript
public readonly grantPrincipal: IPrincipal;
```

- *Type:* aws-cdk-lib.aws_iam.IPrincipal

The principal to grant permissions to.

---

##### `instanceAvailabilityZone`<sup>Required</sup> <a name="instanceAvailabilityZone" id="pwed-cdk.bastion.WindowsBastion.property.instanceAvailabilityZone"></a>

```typescript
public readonly instanceAvailabilityZone: string;
```

- *Type:* string

The availability zone the instance was launched in.

---

##### `instanceId`<sup>Required</sup> <a name="instanceId" id="pwed-cdk.bastion.WindowsBastion.property.instanceId"></a>

```typescript
public readonly instanceId: string;
```

- *Type:* string

The instance's ID.

---

##### `instancePrivateDnsName`<sup>Required</sup> <a name="instancePrivateDnsName" id="pwed-cdk.bastion.WindowsBastion.property.instancePrivateDnsName"></a>

```typescript
public readonly instancePrivateDnsName: string;
```

- *Type:* string

Private DNS name for this instance.

---

##### `instancePrivateIp`<sup>Required</sup> <a name="instancePrivateIp" id="pwed-cdk.bastion.WindowsBastion.property.instancePrivateIp"></a>

```typescript
public readonly instancePrivateIp: string;
```

- *Type:* string

Private IP for this instance.

---

##### `instancePublicDnsName`<sup>Required</sup> <a name="instancePublicDnsName" id="pwed-cdk.bastion.WindowsBastion.property.instancePublicDnsName"></a>

```typescript
public readonly instancePublicDnsName: string;
```

- *Type:* string

Publicly-routable DNS name for this instance.

(May be an empty string if the instance does not have a public name).

---

##### `instancePublicIp`<sup>Required</sup> <a name="instancePublicIp" id="pwed-cdk.bastion.WindowsBastion.property.instancePublicIp"></a>

```typescript
public readonly instancePublicIp: string;
```

- *Type:* string

Publicly-routable IP  address for this instance.

(May be an empty string if the instance does not have a public IP).

---

##### `role`<sup>Required</sup> <a name="role" id="pwed-cdk.bastion.WindowsBastion.property.role"></a>

```typescript
public readonly role: IRole;
```

- *Type:* aws-cdk-lib.aws_iam.IRole

---

##### `securityGroup`<sup>Required</sup> <a name="securityGroup" id="pwed-cdk.bastion.WindowsBastion.property.securityGroup"></a>

```typescript
public readonly securityGroup: ISecurityGroup;
```

- *Type:* aws-cdk-lib.aws_ec2.ISecurityGroup

---


## Structs <a name="Structs" id="Structs"></a>

### BastionAccessPolicyProps <a name="BastionAccessPolicyProps" id="pwed-cdk.bastion.BastionAccessPolicyProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.BastionAccessPolicyProps.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const bastionAccessPolicyProps: bastion.BastionAccessPolicyProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionAccessPolicyProps.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.BastionAccessPolicyProps.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

### BastionInstanceProps <a name="BastionInstanceProps" id="pwed-cdk.bastion.BastionInstanceProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.BastionInstanceProps.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const bastionInstanceProps: bastion.BastionInstanceProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.vpc">vpc</a></code> | <code>aws-cdk-lib.aws_ec2.IVpc</code> | VPC to launch the instance in. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.vpcSubnets">vpcSubnets</a></code> | <code>aws-cdk-lib.aws_ec2.SubnetSelection</code> | Where to place the instance within the VPC. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.blockDevices">blockDevices</a></code> | <code>aws-cdk-lib.aws_ec2.BlockDevice[]</code> | Specifies how block devices are exposed to the instance. You can specify virtual devices and EBS volumes. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.instanceName">instanceName</a></code> | <code>string</code> | The name of the instance. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.instanceType">instanceType</a></code> | <code>aws-cdk-lib.aws_ec2.InstanceType</code> | Type of instance to launch. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.machineImage">machineImage</a></code> | <code>aws-cdk-lib.aws_ec2.IMachineImage</code> | AMI to launch. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.privateIpAddress">privateIpAddress</a></code> | <code>string</code> | Defines a private IP address to associate with an instance. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.role">role</a></code> | <code>aws-cdk-lib.aws_iam.IRole</code> | An IAM role to associate with the instance profile assigned to this Auto Scaling Group. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.securityGroup">securityGroup</a></code> | <code>aws-cdk-lib.aws_ec2.ISecurityGroup</code> | Security Group to assign to this instance. |
| <code><a href="#pwed-cdk.bastion.BastionInstanceProps.property.userData">userData</a></code> | <code>aws-cdk-lib.aws_ec2.UserData</code> | Specific UserData to use. |

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.BastionInstanceProps.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

##### `vpc`<sup>Required</sup> <a name="vpc" id="pwed-cdk.bastion.BastionInstanceProps.property.vpc"></a>

```typescript
public readonly vpc: IVpc;
```

- *Type:* aws-cdk-lib.aws_ec2.IVpc

VPC to launch the instance in.

---

##### `vpcSubnets`<sup>Required</sup> <a name="vpcSubnets" id="pwed-cdk.bastion.BastionInstanceProps.property.vpcSubnets"></a>

```typescript
public readonly vpcSubnets: SubnetSelection;
```

- *Type:* aws-cdk-lib.aws_ec2.SubnetSelection
- *Default:* Private subnets.

Where to place the instance within the VPC.

---

##### `blockDevices`<sup>Optional</sup> <a name="blockDevices" id="pwed-cdk.bastion.BastionInstanceProps.property.blockDevices"></a>

```typescript
public readonly blockDevices: BlockDevice[];
```

- *Type:* aws-cdk-lib.aws_ec2.BlockDevice[]
- *Default:* Uses the block device mapping of the AMI

Specifies how block devices are exposed to the instance. You can specify virtual devices and EBS volumes.

Each instance that is launched has an associated root device volume,
either an Amazon EBS volume or an instance store volume.
You can use block device mappings to specify additional EBS volumes or
instance store volumes to attach to an instance when it is launched.

> [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)

---

##### `instanceName`<sup>Optional</sup> <a name="instanceName" id="pwed-cdk.bastion.BastionInstanceProps.property.instanceName"></a>

```typescript
public readonly instanceName: string;
```

- *Type:* string
- *Default:* CDK generated name

The name of the instance.

---

##### `instanceType`<sup>Optional</sup> <a name="instanceType" id="pwed-cdk.bastion.BastionInstanceProps.property.instanceType"></a>

```typescript
public readonly instanceType: InstanceType;
```

- *Type:* aws-cdk-lib.aws_ec2.InstanceType
- *Default:* t3a.large

Type of instance to launch.

---

##### `machineImage`<sup>Optional</sup> <a name="machineImage" id="pwed-cdk.bastion.BastionInstanceProps.property.machineImage"></a>

```typescript
public readonly machineImage: IMachineImage;
```

- *Type:* aws-cdk-lib.aws_ec2.IMachineImage
- *Default:* latest windows server 2022 full base

AMI to launch.

---

##### `privateIpAddress`<sup>Optional</sup> <a name="privateIpAddress" id="pwed-cdk.bastion.BastionInstanceProps.property.privateIpAddress"></a>

```typescript
public readonly privateIpAddress: string;
```

- *Type:* string
- *Default:* no association

Defines a private IP address to associate with an instance.

Private IP should be available within the VPC that the instance is build within.

---

##### `role`<sup>Optional</sup> <a name="role" id="pwed-cdk.bastion.BastionInstanceProps.property.role"></a>

```typescript
public readonly role: IRole;
```

- *Type:* aws-cdk-lib.aws_iam.IRole
- *Default:* A role will automatically be created, it can be accessed via the `role` property

An IAM role to associate with the instance profile assigned to this Auto Scaling Group.

The role must be assumable by the service principal `ec2.amazonaws.com`:

---

*Example*

```typescript
const role = new iam.Role(this, 'MyRole', {
  assumedBy: new iam.ServicePrincipal('ec2.amazonaws.com')
});
```


##### `securityGroup`<sup>Optional</sup> <a name="securityGroup" id="pwed-cdk.bastion.BastionInstanceProps.property.securityGroup"></a>

```typescript
public readonly securityGroup: ISecurityGroup;
```

- *Type:* aws-cdk-lib.aws_ec2.ISecurityGroup
- *Default:* create new security group

Security Group to assign to this instance.

---

##### `userData`<sup>Optional</sup> <a name="userData" id="pwed-cdk.bastion.BastionInstanceProps.property.userData"></a>

```typescript
public readonly userData: UserData;
```

- *Type:* aws-cdk-lib.aws_ec2.UserData
- *Default:* A UserData object appropriate for the MachineImage's Operating System is created.

Specific UserData to use.

The UserData may still be mutated after creation.

---

### BastionPermissionSetProps <a name="BastionPermissionSetProps" id="pwed-cdk.bastion.BastionPermissionSetProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.BastionPermissionSetProps.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const bastionPermissionSetProps: bastion.BastionPermissionSetProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.instanceArn">instanceArn</a></code> | <code>string</code> | The ARN of the SSO instance under which the operation will be executed. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.name">name</a></code> | <code>string</code> | The name of the permission set. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.customerManagedPolicyReferences">customerManagedPolicyReferences</a></code> | <code>aws-cdk-lib.IResolvable \| aws-cdk-lib.aws_sso.CfnPermissionSet.CustomerManagedPolicyReferenceProperty \| aws-cdk-lib.IResolvable[]</code> | `AWS::SSO::PermissionSet.CustomerManagedPolicyReferences`. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.description">description</a></code> | <code>string</code> | The description of the `PermissionSet` . |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.inlinePolicy">inlinePolicy</a></code> | <code>any</code> | The IAM inline policy that is attached to the permission set. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.managedPolicies">managedPolicies</a></code> | <code>string[]</code> | A structure that stores the details of the IAM managed policy. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.permissionsBoundary">permissionsBoundary</a></code> | <code>aws-cdk-lib.aws_sso.CfnPermissionSet.PermissionsBoundaryProperty \| aws-cdk-lib.IResolvable</code> | `AWS::SSO::PermissionSet.PermissionsBoundary`. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.relayStateType">relayStateType</a></code> | <code>string</code> | Used to redirect users within the application during the federation authentication process. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.sessionDuration">sessionDuration</a></code> | <code>string</code> | The length of time that the application user sessions are valid for in the ISO-8601 standard. |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.tags">tags</a></code> | <code>aws-cdk-lib.CfnTag[]</code> | The tags to attach to the new `PermissionSet` . |
| <code><a href="#pwed-cdk.bastion.BastionPermissionSetProps.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |

---

##### `instanceArn`<sup>Required</sup> <a name="instanceArn" id="pwed-cdk.bastion.BastionPermissionSetProps.property.instanceArn"></a>

```typescript
public readonly instanceArn: string;
```

- *Type:* string

The ARN of the SSO instance under which the operation will be executed.

For more information about ARNs, see [Amazon Resource Names (ARNs) and AWS Service Namespaces](https://docs.aws.amazon.com//general/latest/gr/aws-arns-and-namespaces.html) in the *AWS General Reference* .

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-instancearn](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-instancearn)

---

##### `name`<sup>Required</sup> <a name="name" id="pwed-cdk.bastion.BastionPermissionSetProps.property.name"></a>

```typescript
public readonly name: string;
```

- *Type:* string

The name of the permission set.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-name](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-name)

---

##### `customerManagedPolicyReferences`<sup>Optional</sup> <a name="customerManagedPolicyReferences" id="pwed-cdk.bastion.BastionPermissionSetProps.property.customerManagedPolicyReferences"></a>

```typescript
public readonly customerManagedPolicyReferences: IResolvable | CustomerManagedPolicyReferenceProperty | IResolvable[];
```

- *Type:* aws-cdk-lib.IResolvable | aws-cdk-lib.aws_sso.CfnPermissionSet.CustomerManagedPolicyReferenceProperty | aws-cdk-lib.IResolvable[]

`AWS::SSO::PermissionSet.CustomerManagedPolicyReferences`.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-customermanagedpolicyreferences](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-customermanagedpolicyreferences)

---

##### `description`<sup>Optional</sup> <a name="description" id="pwed-cdk.bastion.BastionPermissionSetProps.property.description"></a>

```typescript
public readonly description: string;
```

- *Type:* string

The description of the `PermissionSet` .

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-description](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-description)

---

##### `inlinePolicy`<sup>Optional</sup> <a name="inlinePolicy" id="pwed-cdk.bastion.BastionPermissionSetProps.property.inlinePolicy"></a>

```typescript
public readonly inlinePolicy: any;
```

- *Type:* any

The IAM inline policy that is attached to the permission set.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-inlinepolicy](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-inlinepolicy)

---

##### `managedPolicies`<sup>Optional</sup> <a name="managedPolicies" id="pwed-cdk.bastion.BastionPermissionSetProps.property.managedPolicies"></a>

```typescript
public readonly managedPolicies: string[];
```

- *Type:* string[]

A structure that stores the details of the IAM managed policy.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-managedpolicies](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-managedpolicies)

---

##### `permissionsBoundary`<sup>Optional</sup> <a name="permissionsBoundary" id="pwed-cdk.bastion.BastionPermissionSetProps.property.permissionsBoundary"></a>

```typescript
public readonly permissionsBoundary: PermissionsBoundaryProperty | IResolvable;
```

- *Type:* aws-cdk-lib.aws_sso.CfnPermissionSet.PermissionsBoundaryProperty | aws-cdk-lib.IResolvable

`AWS::SSO::PermissionSet.PermissionsBoundary`.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-permissionsboundary](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-permissionsboundary)

---

##### `relayStateType`<sup>Optional</sup> <a name="relayStateType" id="pwed-cdk.bastion.BastionPermissionSetProps.property.relayStateType"></a>

```typescript
public readonly relayStateType: string;
```

- *Type:* string

Used to redirect users within the application during the federation authentication process.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-relaystatetype](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-relaystatetype)

---

##### `sessionDuration`<sup>Optional</sup> <a name="sessionDuration" id="pwed-cdk.bastion.BastionPermissionSetProps.property.sessionDuration"></a>

```typescript
public readonly sessionDuration: string;
```

- *Type:* string

The length of time that the application user sessions are valid for in the ISO-8601 standard.

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-sessionduration](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-sessionduration)

---

##### `tags`<sup>Optional</sup> <a name="tags" id="pwed-cdk.bastion.BastionPermissionSetProps.property.tags"></a>

```typescript
public readonly tags: CfnTag[];
```

- *Type:* aws-cdk-lib.CfnTag[]

The tags to attach to the new `PermissionSet` .

> [http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-tags](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-sso-permissionset.html#cfn-sso-permissionset-tags)

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.BastionPermissionSetProps.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

### LinuxBastionProps <a name="LinuxBastionProps" id="pwed-cdk.bastion.LinuxBastionProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.LinuxBastionProps.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const linuxBastionProps: bastion.LinuxBastionProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.vpc">vpc</a></code> | <code>aws-cdk-lib.aws_ec2.IVpc</code> | VPC to launch the instance in. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.vpcSubnets">vpcSubnets</a></code> | <code>aws-cdk-lib.aws_ec2.SubnetSelection</code> | Where to place the instance within the VPC. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.blockDevices">blockDevices</a></code> | <code>aws-cdk-lib.aws_ec2.BlockDevice[]</code> | Specifies how block devices are exposed to the instance. You can specify virtual devices and EBS volumes. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.instanceName">instanceName</a></code> | <code>string</code> | The name of the instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.instanceType">instanceType</a></code> | <code>aws-cdk-lib.aws_ec2.InstanceType</code> | Type of instance to launch. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.machineImage">machineImage</a></code> | <code>aws-cdk-lib.aws_ec2.IMachineImage</code> | AMI to launch. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.privateIpAddress">privateIpAddress</a></code> | <code>string</code> | Defines a private IP address to associate with an instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.role">role</a></code> | <code>aws-cdk-lib.aws_iam.IRole</code> | An IAM role to associate with the instance profile assigned to this Auto Scaling Group. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.securityGroup">securityGroup</a></code> | <code>aws-cdk-lib.aws_ec2.ISecurityGroup</code> | Security Group to assign to this instance. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.userData">userData</a></code> | <code>aws-cdk-lib.aws_ec2.UserData</code> | Specific UserData to use. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.packageManager">packageManager</a></code> | <code>pwed-cdk.bastion.LinuxPackageManager</code> | Package manager used for installing packages. |
| <code><a href="#pwed-cdk.bastion.LinuxBastionProps.property.packages">packages</a></code> | <code>string[]</code> | List of packages to be installed as part of the userdata using winget. |

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.LinuxBastionProps.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

##### `vpc`<sup>Required</sup> <a name="vpc" id="pwed-cdk.bastion.LinuxBastionProps.property.vpc"></a>

```typescript
public readonly vpc: IVpc;
```

- *Type:* aws-cdk-lib.aws_ec2.IVpc

VPC to launch the instance in.

---

##### `vpcSubnets`<sup>Required</sup> <a name="vpcSubnets" id="pwed-cdk.bastion.LinuxBastionProps.property.vpcSubnets"></a>

```typescript
public readonly vpcSubnets: SubnetSelection;
```

- *Type:* aws-cdk-lib.aws_ec2.SubnetSelection
- *Default:* Private subnets.

Where to place the instance within the VPC.

---

##### `blockDevices`<sup>Optional</sup> <a name="blockDevices" id="pwed-cdk.bastion.LinuxBastionProps.property.blockDevices"></a>

```typescript
public readonly blockDevices: BlockDevice[];
```

- *Type:* aws-cdk-lib.aws_ec2.BlockDevice[]
- *Default:* Uses the block device mapping of the AMI

Specifies how block devices are exposed to the instance. You can specify virtual devices and EBS volumes.

Each instance that is launched has an associated root device volume,
either an Amazon EBS volume or an instance store volume.
You can use block device mappings to specify additional EBS volumes or
instance store volumes to attach to an instance when it is launched.

> [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)

---

##### `instanceName`<sup>Optional</sup> <a name="instanceName" id="pwed-cdk.bastion.LinuxBastionProps.property.instanceName"></a>

```typescript
public readonly instanceName: string;
```

- *Type:* string
- *Default:* CDK generated name

The name of the instance.

---

##### `instanceType`<sup>Optional</sup> <a name="instanceType" id="pwed-cdk.bastion.LinuxBastionProps.property.instanceType"></a>

```typescript
public readonly instanceType: InstanceType;
```

- *Type:* aws-cdk-lib.aws_ec2.InstanceType
- *Default:* t3a.large

Type of instance to launch.

---

##### `machineImage`<sup>Optional</sup> <a name="machineImage" id="pwed-cdk.bastion.LinuxBastionProps.property.machineImage"></a>

```typescript
public readonly machineImage: IMachineImage;
```

- *Type:* aws-cdk-lib.aws_ec2.IMachineImage
- *Default:* latest windows server 2022 full base

AMI to launch.

---

##### `privateIpAddress`<sup>Optional</sup> <a name="privateIpAddress" id="pwed-cdk.bastion.LinuxBastionProps.property.privateIpAddress"></a>

```typescript
public readonly privateIpAddress: string;
```

- *Type:* string
- *Default:* no association

Defines a private IP address to associate with an instance.

Private IP should be available within the VPC that the instance is build within.

---

##### `role`<sup>Optional</sup> <a name="role" id="pwed-cdk.bastion.LinuxBastionProps.property.role"></a>

```typescript
public readonly role: IRole;
```

- *Type:* aws-cdk-lib.aws_iam.IRole
- *Default:* A role will automatically be created, it can be accessed via the `role` property

An IAM role to associate with the instance profile assigned to this Auto Scaling Group.

The role must be assumable by the service principal `ec2.amazonaws.com`:

---

*Example*

```typescript
const role = new iam.Role(this, 'MyRole', {
  assumedBy: new iam.ServicePrincipal('ec2.amazonaws.com')
});
```


##### `securityGroup`<sup>Optional</sup> <a name="securityGroup" id="pwed-cdk.bastion.LinuxBastionProps.property.securityGroup"></a>

```typescript
public readonly securityGroup: ISecurityGroup;
```

- *Type:* aws-cdk-lib.aws_ec2.ISecurityGroup
- *Default:* create new security group

Security Group to assign to this instance.

---

##### `userData`<sup>Optional</sup> <a name="userData" id="pwed-cdk.bastion.LinuxBastionProps.property.userData"></a>

```typescript
public readonly userData: UserData;
```

- *Type:* aws-cdk-lib.aws_ec2.UserData
- *Default:* A UserData object appropriate for the MachineImage's Operating System is created.

Specific UserData to use.

The UserData may still be mutated after creation.

---

##### `packageManager`<sup>Optional</sup> <a name="packageManager" id="pwed-cdk.bastion.LinuxBastionProps.property.packageManager"></a>

```typescript
public readonly packageManager: LinuxPackageManager;
```

- *Type:* pwed-cdk.bastion.LinuxPackageManager
- *Default:* dnf

Package manager used for installing packages.

---

##### `packages`<sup>Optional</sup> <a name="packages" id="pwed-cdk.bastion.LinuxBastionProps.property.packages"></a>

```typescript
public readonly packages: string[];
```

- *Type:* string[]
- *Default:* []

List of packages to be installed as part of the userdata using winget.

---

### ScheduleShutdownProps <a name="ScheduleShutdownProps" id="pwed-cdk.bastion.ScheduleShutdownProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.ScheduleShutdownProps.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const scheduleShutdownProps: bastion.ScheduleShutdownProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdownProps.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdownProps.property.shutdownSchedule">shutdownSchedule</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.ScheduleShutdownProps.property.timezone">timezone</a></code> | <code>string</code> | *No description.* |

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.ScheduleShutdownProps.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

##### `shutdownSchedule`<sup>Optional</sup> <a name="shutdownSchedule" id="pwed-cdk.bastion.ScheduleShutdownProps.property.shutdownSchedule"></a>

```typescript
public readonly shutdownSchedule: string;
```

- *Type:* string

---

##### `timezone`<sup>Optional</sup> <a name="timezone" id="pwed-cdk.bastion.ScheduleShutdownProps.property.timezone"></a>

```typescript
public readonly timezone: string;
```

- *Type:* string

---

### SecurityTagable <a name="SecurityTagable" id="pwed-cdk.bastion.SecurityTagable"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.SecurityTagable.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const securityTagable: bastion.SecurityTagable = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.SecurityTagable.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.SecurityTagable.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

### StaticSiteProps <a name="StaticSiteProps" id="pwed-cdk.static_site.StaticSiteProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.static_site.StaticSiteProps.Initializer"></a>

```typescript
import { static_site } from 'pwed-cdk'

const staticSiteProps: static_site.StaticSiteProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.static_site.StaticSiteProps.property.domain">domain</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSiteProps.property.path">path</a></code> | <code>string</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSiteProps.property.alternativeDomains">alternativeDomains</a></code> | <code>string[]</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSiteProps.property.alternativeHostedZones">alternativeHostedZones</a></code> | <code>aws-cdk-lib.aws_route53.IHostedZone[]</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSiteProps.property.enablePrettyPaths">enablePrettyPaths</a></code> | <code>boolean</code> | *No description.* |
| <code><a href="#pwed-cdk.static_site.StaticSiteProps.property.hostedZone">hostedZone</a></code> | <code>aws-cdk-lib.aws_route53.IHostedZone</code> | *No description.* |

---

##### `domain`<sup>Required</sup> <a name="domain" id="pwed-cdk.static_site.StaticSiteProps.property.domain"></a>

```typescript
public readonly domain: string;
```

- *Type:* string

---

##### `path`<sup>Required</sup> <a name="path" id="pwed-cdk.static_site.StaticSiteProps.property.path"></a>

```typescript
public readonly path: string;
```

- *Type:* string

---

##### `alternativeDomains`<sup>Optional</sup> <a name="alternativeDomains" id="pwed-cdk.static_site.StaticSiteProps.property.alternativeDomains"></a>

```typescript
public readonly alternativeDomains: string[];
```

- *Type:* string[]

---

##### `alternativeHostedZones`<sup>Optional</sup> <a name="alternativeHostedZones" id="pwed-cdk.static_site.StaticSiteProps.property.alternativeHostedZones"></a>

```typescript
public readonly alternativeHostedZones: IHostedZone[];
```

- *Type:* aws-cdk-lib.aws_route53.IHostedZone[]

---

##### `enablePrettyPaths`<sup>Optional</sup> <a name="enablePrettyPaths" id="pwed-cdk.static_site.StaticSiteProps.property.enablePrettyPaths"></a>

```typescript
public readonly enablePrettyPaths: boolean;
```

- *Type:* boolean

---

##### `hostedZone`<sup>Optional</sup> <a name="hostedZone" id="pwed-cdk.static_site.StaticSiteProps.property.hostedZone"></a>

```typescript
public readonly hostedZone: IHostedZone;
```

- *Type:* aws-cdk-lib.aws_route53.IHostedZone

---

### TtlProps <a name="TtlProps" id="pwed-cdk.ttl.TtlProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.ttl.TtlProps.Initializer"></a>

```typescript
import { ttl } from 'pwed-cdk'

const ttlProps: ttl.TtlProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.ttl.TtlProps.property.ttl">ttl</a></code> | <code>aws-cdk-lib.Duration</code> | *No description.* |
| <code><a href="#pwed-cdk.ttl.TtlProps.property.pollInterval">pollInterval</a></code> | <code>aws-cdk-lib.Duration</code> | *No description.* |

---

##### `ttl`<sup>Required</sup> <a name="ttl" id="pwed-cdk.ttl.TtlProps.property.ttl"></a>

```typescript
public readonly ttl: Duration;
```

- *Type:* aws-cdk-lib.Duration

---

##### `pollInterval`<sup>Optional</sup> <a name="pollInterval" id="pwed-cdk.ttl.TtlProps.property.pollInterval"></a>

```typescript
public readonly pollInterval: Duration;
```

- *Type:* aws-cdk-lib.Duration

---

### WindowsBastionProps <a name="WindowsBastionProps" id="pwed-cdk.bastion.WindowsBastionProps"></a>

#### Initializer <a name="Initializer" id="pwed-cdk.bastion.WindowsBastionProps.Initializer"></a>

```typescript
import { bastion } from 'pwed-cdk'

const windowsBastionProps: bastion.WindowsBastionProps = { ... }
```

#### Properties <a name="Properties" id="Properties"></a>

| **Name** | **Type** | **Description** |
| --- | --- | --- |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.securityTag">securityTag</a></code> | <code>aws-cdk-lib.Tag</code> | Tag used by all bastion resources for managing access to resources. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.vpc">vpc</a></code> | <code>aws-cdk-lib.aws_ec2.IVpc</code> | VPC to launch the instance in. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.vpcSubnets">vpcSubnets</a></code> | <code>aws-cdk-lib.aws_ec2.SubnetSelection</code> | Where to place the instance within the VPC. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.blockDevices">blockDevices</a></code> | <code>aws-cdk-lib.aws_ec2.BlockDevice[]</code> | Specifies how block devices are exposed to the instance. You can specify virtual devices and EBS volumes. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.instanceName">instanceName</a></code> | <code>string</code> | The name of the instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.instanceType">instanceType</a></code> | <code>aws-cdk-lib.aws_ec2.InstanceType</code> | Type of instance to launch. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.machineImage">machineImage</a></code> | <code>aws-cdk-lib.aws_ec2.IMachineImage</code> | AMI to launch. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.privateIpAddress">privateIpAddress</a></code> | <code>string</code> | Defines a private IP address to associate with an instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.role">role</a></code> | <code>aws-cdk-lib.aws_iam.IRole</code> | An IAM role to associate with the instance profile assigned to this Auto Scaling Group. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.securityGroup">securityGroup</a></code> | <code>aws-cdk-lib.aws_ec2.ISecurityGroup</code> | Security Group to assign to this instance. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.userData">userData</a></code> | <code>aws-cdk-lib.aws_ec2.UserData</code> | Specific UserData to use. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.createKeyPair">createKeyPair</a></code> | <code>boolean</code> | If a keypair should be created and saved into Secrets Manager. |
| <code><a href="#pwed-cdk.bastion.WindowsBastionProps.property.windowsPackages">windowsPackages</a></code> | <code>string[]</code> | List of packages to be installed as part of the userdata using winget. |

---

##### `securityTag`<sup>Optional</sup> <a name="securityTag" id="pwed-cdk.bastion.WindowsBastionProps.property.securityTag"></a>

```typescript
public readonly securityTag: Tag;
```

- *Type:* aws-cdk-lib.Tag
- *Default:* {Key: "security:bastion", value: "true"}

Tag used by all bastion resources for managing access to resources.

---

##### `vpc`<sup>Required</sup> <a name="vpc" id="pwed-cdk.bastion.WindowsBastionProps.property.vpc"></a>

```typescript
public readonly vpc: IVpc;
```

- *Type:* aws-cdk-lib.aws_ec2.IVpc

VPC to launch the instance in.

---

##### `vpcSubnets`<sup>Required</sup> <a name="vpcSubnets" id="pwed-cdk.bastion.WindowsBastionProps.property.vpcSubnets"></a>

```typescript
public readonly vpcSubnets: SubnetSelection;
```

- *Type:* aws-cdk-lib.aws_ec2.SubnetSelection
- *Default:* Private subnets.

Where to place the instance within the VPC.

---

##### `blockDevices`<sup>Optional</sup> <a name="blockDevices" id="pwed-cdk.bastion.WindowsBastionProps.property.blockDevices"></a>

```typescript
public readonly blockDevices: BlockDevice[];
```

- *Type:* aws-cdk-lib.aws_ec2.BlockDevice[]
- *Default:* Uses the block device mapping of the AMI

Specifies how block devices are exposed to the instance. You can specify virtual devices and EBS volumes.

Each instance that is launched has an associated root device volume,
either an Amazon EBS volume or an instance store volume.
You can use block device mappings to specify additional EBS volumes or
instance store volumes to attach to an instance when it is launched.

> [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)

---

##### `instanceName`<sup>Optional</sup> <a name="instanceName" id="pwed-cdk.bastion.WindowsBastionProps.property.instanceName"></a>

```typescript
public readonly instanceName: string;
```

- *Type:* string
- *Default:* CDK generated name

The name of the instance.

---

##### `instanceType`<sup>Optional</sup> <a name="instanceType" id="pwed-cdk.bastion.WindowsBastionProps.property.instanceType"></a>

```typescript
public readonly instanceType: InstanceType;
```

- *Type:* aws-cdk-lib.aws_ec2.InstanceType
- *Default:* t3a.large

Type of instance to launch.

---

##### `machineImage`<sup>Optional</sup> <a name="machineImage" id="pwed-cdk.bastion.WindowsBastionProps.property.machineImage"></a>

```typescript
public readonly machineImage: IMachineImage;
```

- *Type:* aws-cdk-lib.aws_ec2.IMachineImage
- *Default:* latest windows server 2022 full base

AMI to launch.

---

##### `privateIpAddress`<sup>Optional</sup> <a name="privateIpAddress" id="pwed-cdk.bastion.WindowsBastionProps.property.privateIpAddress"></a>

```typescript
public readonly privateIpAddress: string;
```

- *Type:* string
- *Default:* no association

Defines a private IP address to associate with an instance.

Private IP should be available within the VPC that the instance is build within.

---

##### `role`<sup>Optional</sup> <a name="role" id="pwed-cdk.bastion.WindowsBastionProps.property.role"></a>

```typescript
public readonly role: IRole;
```

- *Type:* aws-cdk-lib.aws_iam.IRole
- *Default:* A role will automatically be created, it can be accessed via the `role` property

An IAM role to associate with the instance profile assigned to this Auto Scaling Group.

The role must be assumable by the service principal `ec2.amazonaws.com`:

---

*Example*

```typescript
const role = new iam.Role(this, 'MyRole', {
  assumedBy: new iam.ServicePrincipal('ec2.amazonaws.com')
});
```


##### `securityGroup`<sup>Optional</sup> <a name="securityGroup" id="pwed-cdk.bastion.WindowsBastionProps.property.securityGroup"></a>

```typescript
public readonly securityGroup: ISecurityGroup;
```

- *Type:* aws-cdk-lib.aws_ec2.ISecurityGroup
- *Default:* create new security group

Security Group to assign to this instance.

---

##### `userData`<sup>Optional</sup> <a name="userData" id="pwed-cdk.bastion.WindowsBastionProps.property.userData"></a>

```typescript
public readonly userData: UserData;
```

- *Type:* aws-cdk-lib.aws_ec2.UserData
- *Default:* A UserData object appropriate for the MachineImage's Operating System is created.

Specific UserData to use.

The UserData may still be mutated after creation.

---

##### `createKeyPair`<sup>Optional</sup> <a name="createKeyPair" id="pwed-cdk.bastion.WindowsBastionProps.property.createKeyPair"></a>

```typescript
public readonly createKeyPair: boolean;
```

- *Type:* boolean
- *Default:* false

If a keypair should be created and saved into Secrets Manager.

This can be used to get Administrator user access

---

##### `windowsPackages`<sup>Optional</sup> <a name="windowsPackages" id="pwed-cdk.bastion.WindowsBastionProps.property.windowsPackages"></a>

```typescript
public readonly windowsPackages: string[];
```

- *Type:* string[]
- *Default:* no association

List of packages to be installed as part of the userdata using winget.

---



## Enums <a name="Enums" id="Enums"></a>

### LinuxPackageManager <a name="LinuxPackageManager" id="pwed-cdk.bastion.LinuxPackageManager"></a>

#### Members <a name="Members" id="Members"></a>

| **Name** | **Description** |
| --- | --- |
| <code><a href="#pwed-cdk.bastion.LinuxPackageManager.APT">APT</a></code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.LinuxPackageManager.YUM">YUM</a></code> | *No description.* |
| <code><a href="#pwed-cdk.bastion.LinuxPackageManager.DNF">DNF</a></code> | *No description.* |

---

##### `APT` <a name="APT" id="pwed-cdk.bastion.LinuxPackageManager.APT"></a>

---


##### `YUM` <a name="YUM" id="pwed-cdk.bastion.LinuxPackageManager.YUM"></a>

---


##### `DNF` <a name="DNF" id="pwed-cdk.bastion.LinuxPackageManager.DNF"></a>

---

