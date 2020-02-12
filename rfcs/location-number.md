# Specification for Location Number (L/N)

**Note:** All spaces in format strings (like this: `NNNNNN`) are only for clarification, and should not appear in practice.

    T NNNNNNN Y MMMMMMM
    ^~~~~~~~~ ^~~~~~~~~
    + L/N-P   + L/N-S

In which:

- `T`: Type.
- `Y`: Subtype.
- `N`: Type-defined fields.
- `M`: Subtype-defined fields.

With the two parts of a L/N:

- **L/N-P**: L/N prefix; the first 8 characters representing a door sign in the UIC campus.
- **L/N-S**: L/N suffix; the last 8 characters for inner use.

The two parts may be used separately.

## General Specifications

- A (full-length) L/N has 16 characters.
- A L/N has a fixed length because L/N-P and L/N-S have fixed lengths.
- The type (`T`) field of a L/N (or L/N-P) cannot be digit 0.
- The subtype (`Y`) field of a L/N (or L/N-S) cannot be digit 0.
- A L/N (or L/N-P) is assigned based on the location designator made by UIC ECDO.

## Format

## Types (`T`)

- `A`: Administration building; "AD".
- `H`: University hall; "TH".
- `T`: Teaching building; "T".
- `V`: Village building; "V".

### Type "AD" (Administration Building) Defined Field [N]

Todo: not defined due to the unknown status of door sign allocation in the administration building.

### Type "TH" (University Hall) Defined Field [N]

    __ FF RR S

In which:

- `_`: Reserved. This should be `0`.
- `F`: Floor number.
    - e.g. `01`
- `R`: Room number.
    - e.g. `03`
- `S`: Section number (if applicable; otherwise this field should be reserved (be `0`)).
    - e.g. `A`

### Type "T" (Teaching Building) Defined Field [N]

    BB FF RR S

In which:

- `B`: Building number.
    - e.g. `08`
- `F`: Floor number.
    - e.g. `03`
- `R`: Room number.
    - e.g. `07`
- `S`: Section number (if applicable; otherwise this field should be reserved (be `0`)).
    - e.g. `A`

### Type "V" (Village Building) Defined Field [N]

    BB FF RR _

In which:

- `B`: Building number.
    - e.g. `27`
- `F`: Floor number.
    - e.g. `07`
- `R`: Room number.
    - e.g. `31`
- `_`: Reserved. This should be `0`.

## Subtypes (`Y`)

- `H`: Shelf.
- `S`: Seat.

### Subtype Shelf (`H`) Defined Field [M]

    _ SS RR PP

In which:

- `_`: Reserved. This should be `0`.
- `S`: Shelf number.
- `R`: Row number.
- `P`: Position number.

### Subtype Seat (`S`) Defined Field [M]

    ___ WW SS

In which:

- `_`: Reserved. This should be `0`.
- `W`: Workspace number (if applicable; otherwise this field should be reserved (be `0`)).
- `S`: Seat number.
