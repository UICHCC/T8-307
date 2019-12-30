# Specification for Location Number (L/N)

        TBBFFRRSYNNNNNN

In which:

- `T`: Type.
- `B`: Building.
- `F`: Floor.
- `R`: Room.
- `S`: Section.
- `Y`: Subtype.
- `N`: Type-defined fields.

## General Specifications

- A L/N has 15 characters.
- A L/N has a fixed length.
- The type (`T`) field of a L/N cannot be digit 0.
- The subtype (`Y`) field of a L/N cannot be digit 0.
- A L/N is assigned based on the location designator made by UIC ECDO.

## Format

A L/N consists of two parts:

- **L/N-P**: L/N prefix; the first 8 characters representing a door sign in the UIC campus.
- **L/N-S**: L/N suffix; the last 7 characters for inner use.

The two parts may be used separately.

## Types (`T`)

- `A`: Administration building; "AD".
- `H`: University hall; "TH".
- `T`: Teaching building; "T".
- `V`: Village building; "V".

## Subtypes (`Y`)

- `H`: Shelf.
- `S`: Seat.

### Subtype Shelf (`H`) Defined Field

        SSRRPP

In which:

- `S`: Shelf number.
- `R`: Row number.
- `P`: Position number.

### Subtype Seat (`S`) Defined Field

        WWRRSS

In which:

- `W`: Workspace number.
- `R`: Reserved.
- `S`: Seat number.
