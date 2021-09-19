# virtual-fort-snelling

The new home of the virtual fort snelling project.

## 1. Requirements

- Git (any recent version, `2.30.1` works for sure)
- Blender (no earlier than `v2.83.5`)
    - Download from the [Blender Archive](https://download.blender.org/release/Blender2.83/)
- Unity `2020.3.16f1`
    - Download from the [Unity Archive](https://unity3d.com/unity/whats-new/2020.3.16) if no longer available in the Unity Hub

## 2. Setup

1. Download and install the required programs listed above.
2. Clone the repository
    - `git clone git@github.umn.edu:history-xr-projects/virtual-fort-snelling.git`
3. Open the `virtual-fort-snelling/unity/virtual-fort-snelling` directory as a Unity project.

## 3. Terminology

There are a few concepts that you should understand before you begin working on this project.

### 3.1 Historical Entity

A historical entity is any object that exists for a given period (or periods) of time.

> A conceptual example of a historical entity might be "The commander's house from 1824 to 1903". 

Historical entities are identified by a unique string ID. This string ID is used in many places throughout the project, so it's important that you spell them correctly and consistantly.

It is crucial that no two historical entities share the same ID. All historical entity IDs must be unique.

> An example of a historical entity ID might be `commanders-house-1824-1903`

A historical entity encompasses an object over a range of time, under the assumption that the object does not change over that range.

For an object that changes over time, multiple historical entities should be designated to it (each corresponding to a unique state of the object).

> For example, the commander's house exists in roughly three states:
> 1. The original structure
> 2. The porch that was added later
> 3. The stucco remodel in 1904
>
> To account for this, we designate three unique historical entities, each encompassing different time period(s)
> - `commanders-house-original`
>   - 1824 – 1903
>   - 1966 – present
> - `commanders-house-porch`
>   - 1840 – 1903
> - `commanders-house-remodel`
>   - 1904 - 1965

**Historical entities are stored in `unity/virtual-fort-snelling/Assets/vfs/Historical Entities/Database/historical-entities.hejson`**

### 3.2 Landmark

A landmark is a collection of one or more related historical entities.

> A conceptual example of a landmark is "The commander's house".

Like historical entities, landmarks are also identified by a unique string ID.

> An example of a landmark ID might be `commanders-house`

A landmark encompasses all historical entity representations of an object.

> For example, the commander's house has three historical entities associated with it, and all are contained within the commander's house landmark.
> - `commanders-house` (landmark)
>   - `commanders-house-original` (historical entity)
>   - `commanders-house-porch` (historical entity)
>   - `commanders-house-remodel` (historical entity)

A landmark can optionally contain an entry in the menu with additional contextual information, history, media, etc.

> Please note that a historical entity need not be contained by any landmark, but every landmark must contain at least one historical entity.

**Landmarks are stored in `unity/virtual-fort-snelling/Assets/vfs/Landmarks/Database/landmarks.ljson`**

## 4. Working

Now that you have a grasp on how the project is structured, ...

TODO: section on updating the main blender file and exporting it to Unity

TODO: section on updating the historical entities database

TODO: section on updating the landmarks database

TODO: section on updating the menu