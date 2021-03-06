## API Report File for "@bentley/presentation-testing"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { Content } from '@bentley/presentation-common';
import { HierarchyCacheMode } from '@bentley/presentation-backend';
import { IModelApp } from '@bentley/imodeljs-frontend';
import { IModelAppOptions } from '@bentley/imodeljs-frontend';
import { IModelConnection } from '@bentley/imodeljs-frontend';
import { InstanceKey } from '@bentley/presentation-common';
import { KeySet } from '@bentley/presentation-common';
import { Omit } from '@bentley/presentation-common';
import { PageOptions } from '@bentley/presentation-common';
import { PresentationManagerProps as PresentationBackendProps } from '@bentley/presentation-backend';
import { PresentationManagerMode } from '@bentley/presentation-backend';
import { PresentationManagerProps } from '@bentley/presentation-frontend';
import { PropertyRecord } from '@bentley/ui-abstract';
import { Ruleset } from '@bentley/presentation-common';
import { TreeNodeItem } from '@bentley/ui-components';

// @public
export class ContentBuilder {
    constructor(props: ContentBuilderProps);
    createContent(rulesetOrId: Ruleset | string, instanceKeys: InstanceKey[], displayType?: string): Promise<PropertyRecord[]>;
    createContentForAllInstances(rulesetOrId: Ruleset | string, displayType?: string): Promise<ContentBuilderResult[]>;
    createContentForInstancePerClass(rulesetOrId: Ruleset | string, displayType?: string): Promise<ContentBuilderResult[]>;
    }

// @public
export interface ContentBuilderProps {
    dataProvider?: IContentBuilderDataProvider;
    imodel: IModelConnection;
}

// @public
export interface ContentBuilderResult {
    className: string;
    records: PropertyRecord[];
}

// @public
export class HierarchyBuilder {
    constructor(props: HierarchyBuilderProps);
    createHierarchy(rulesetOrId: Ruleset | string): Promise<HierarchyNode[]>;
    }

// @public
export interface HierarchyBuilderProps {
    imodel: IModelConnection;
    nodeMappingFunc?: NodeMappingFunc;
}

export { HierarchyCacheMode }

// @public
export interface HierarchyNode extends Omit<MappedNode, "children"> {
    children?: HierarchyNode[];
}

// @public
export interface IContentBuilderDataProvider {
    getContent: (options?: PageOptions) => Promise<Readonly<Content> | undefined>;
    getContentSetSize: () => Promise<number>;
    keys: Readonly<KeySet>;
}

// @public
export const initialize: (props?: PresentationTestingInitProps | undefined) => Promise<void>;

// @public
export interface MappedNode {
    [index: string]: any;
    children?: never;
}

// @public
export type NodeMappingFunc = (node: TreeNodeItem) => MappedNode;

export { PresentationBackendProps }

export { PresentationManagerMode }

// @public (undocumented)
export interface PresentationTestingInitProps {
    backendProps?: PresentationBackendProps;
    frontendApp?: {
        startup: (opts?: IModelAppOptions) => Promise<void>;
    };
    frontendAppOptions?: IModelAppOptions;
    frontendProps?: PresentationManagerProps;
}

// @public
export const terminate: (frontendApp?: typeof IModelApp) => Promise<void>;


// (No @packageDocumentation comment for this package)

```
